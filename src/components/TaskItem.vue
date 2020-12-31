<template>
    <div class="task" :class="{ closed: isCompleted }">
        <p class="task-content"> {{ content }} </p>
        <input type="checkbox" v-model="isCompleted">
    </div>
</template>

<script>
export default {
    name:'TaskItem',
    data() {
        return {
            isCompleted: false
        }
    },
    props: {
        content: {
            type: String,
            required: true
        }
    }
}
</script>

<style scoped>
/* Style d'une tache */
.task{
    box-shadow: 0 0 3px #7e7e7ed0;
    border-radius: 4px;
    box-sizing: border-box;
    padding: .5em 1em;
    font-family: 'Spartan', cursive;
    margin-bottom: 1em;
    display: flex;
    align-items: center;
}

.task.closed .task-content{
    text-decoration: line-through;
    color: #7e7e7ed0;
}

.task .task-content{
    flex-basis: 90%;
    transition: all ease-in .6s;
}
</style>
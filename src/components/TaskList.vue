<template>
    <div class="tasks">
        <TaskItem v-for="(task, id) in tasks" :content="task" :key="id" />
    </div>
</template>

<script>
import TaskItem from './TaskItem'

export default {
    name:'TaskList',
    props:{
        tasks:{
            type: Array,
            required: true
        }
    },
    components: {
        TaskItem
    }
}
</script>

<style scoped>
.tasks{
    width: 60%;
    margin: auto;
    margin-top: 1em;
}
</style>
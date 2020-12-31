<template>
  <form class="form-control" @submit.prevent="onAddTask">
      <div class="form-group">
            <input type="text" class="input" v-model="task" placeholder="Quelles sont les taches a faire ?" />
            <input type="submit" class="button" value="Ajouter">
      </div>
  </form>
</template>

<script>
export default {
    name:'TaskForm',
    data(){
        return {
            task:''
        }
    },
    emits:{
        'add-task': (task) => {
            if (task.length === 0) {
                console.warn('Error: Invalid Task Submitted')
                return false
            }

            return true
        }
    },
    methods: {
        onAddTask(){
            // On emet l'evenement pour la mise a jour de la liste
            this.$emit('add-task', this.task)

            // On reinitialise la valeur de la tache
            this.task = ''
        }
    }
}
</script>

<style scoped>

.form-group{
    display: flex;
    justify-content: center;
}

.form-group .input{
    flex-basis: 30%;
    border: 1px solid #c7c7c7;
    outline: none;
    font-family: 'Spartan', cursive;
    padding: 1em 1em;
}

.form-group .button{
    background-color: #D8D174;
    border: none;
    border-radius: none;
    outline: none;
    cursor: pointer;
    letter-spacing: 1px;
    padding: .5em 1em;
    box-sizing: border-box;
}
</style>
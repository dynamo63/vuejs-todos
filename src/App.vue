<template>
  <h1 class="title">Liste de Tache</h1>
  <TaskForm  @add-task="updateTasks"/>
  <TaskList :tasks="todos" />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TaskForm from './components/TaskForm'
import TaskList from './components/TaskList'

export default {
  name: 'App',
  components:{
    TaskForm, TaskList
  },
  data(){
    return {
      todos:['Apprendre VueJs', 'Apprendre Vue-cli', 'Apprendre Vue-router']
    }
  },
  methods: {
    updateTasks(task){
      this.todos.push(task)
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Spartan&display=swap');

body{
  margin: 0;
  padding: 0;
}

.title{
  text-align: center;
  font-family: 'Spartan', cursive;
}

</style>

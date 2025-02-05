<script setup>
import TaskFinishedBar from './components/TaskFinishedBar.vue';
import CreateTask from './components/CreateTask.vue';
import Tasks from './components/Tasks.vue';

</script>

<template>
  <div class="container">
    <TaskFinishedBar :tasks="tasks" :tasksProgress="tasksProgress" :progressBar="progressBar" />
    <CreateTask :newTask="newTask" :generateTask="generateTask" />
    <Tasks :tasksArray="tasksArray" :deleteTask="deleteTask" />
  </div>
</template>

<script>
  export default {
    name: 'Root',
    data() {
      return {
        tasks: 'Tarefas',
        tasksProgress: 100,
        newTask: '',
        tasksArray: []
      }
    },
    methods: {
      generateTask(task){
        const newTask = {
          id: this.uid(),
          resolved: false,
          task: task
        }

       this.tasksArray.push(newTask)

      },

      uid() {
        return Date.now().toString(36) + Math.random().toString(36).substr(2);
      }, 

      deleteTask(index) {
        this.tasksArray = this.tasksArray.filter((e) => e.id !== index)             
      },

      progressBar() {
        // primeiro vou ter que achar a quantidade de tasks que estão com resolved === true (guardar numa variável)
        // pegar a quantidade total de elementos no array

        // finalizar com o calculo de porcentagem (final - inicial * 100)
      }
    }
  }
</script>

<style>
  @import url('./style/reset.css');
  @import url('./style/App.css');
</style>

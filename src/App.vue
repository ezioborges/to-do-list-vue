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
        tasksProgress: 0,
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
        const taskDone = this.tasksArray.filter((e) => e.resolved === true);
        const calcTaskDone = (taskDone.length / this.tasksArray.length) * 100;
        console.log("🚀 ~ progressBar ~ taskDone:", calcTaskDone)

        return calcTaskDone
      }
    }
  }
</script>

<style>
  @import url('./style/reset.css');
  @import url('./style/App.css');
</style>

<script setup>
import TaskFinishedBar from './components/TaskFinishedBar.vue';
import CreateTask from './components/CreateTask.vue';
import Tasks from './components/Tasks.vue';

</script>

<template>
  <div class="container">
    <TaskFinishedBar :tasks="tasks" :tasksProgress="tasksProgress" />
    <CreateTask :newTask="newTask" :generateTask="generateTask" />
    <Tasks :tasksArray="tasksArray" />
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
       this.tasksArray.push(task)
      }
    }
  }
</script>

<style>
  @import url('./style/reset.css');
  @import url('./style/App.css');
</style>

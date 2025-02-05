<template>
    <div class="tasks-content">
        <h1 class="tasks-title">{{tasks}}</h1>
        <div class="tasks-bar">{{ progressBar() }}%</div>
    </div>
</template>

<script>
    export default {
        name:'TaskFinishedBar',
        props: ['tasks', 'tasksProgress', 'progressBar']
    }
</script>

<style>
    @import url('../style/task-finished-bar.css');
</style>
<template>
    <div class="tasks-content">
        <h1 class="tasks-title">{{tasks}}</h1>
        <div class="tasks-bar">{{ tasksProgress }}%</div>
    </div>
</template>

<script>
    export default {
        name:'TaskFinishedBar',
        props: ['tasks', 'tasksProgress']
    }
</script>

<style>
    @import url('../style/task-finished-bar.css');
</style>
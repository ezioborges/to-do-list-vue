<template>
    <div class="tasks-content">
        <h1 class="tasks-title">{{tasks}}</h1>
        <div class="tasks-bar">
            <div class="task-bg" :style="{width: progressBar() + '%'}">
                <p class="barPercent">{{ progressBar() ? progressBar() : 0}}%</p>
            </div>
        </div>
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
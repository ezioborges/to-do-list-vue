<template>
    <div class="to-do-item">
            <div class="border-item"></div>
            <div class="item-desc">
                <p>{{task}}</p>
            </div>
        </div>
</template>

<script>
    export default {
        name: 'TasksCard',
        props: ['tasksArray', 'task']
    }
</script>

<style>
    @import url('../style/tasks.css');
</style>
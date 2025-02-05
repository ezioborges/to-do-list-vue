<template>
    <div
        class="to-do-item"
        :class="[task.resolved ? 'to-do-item-done' : 'to-do-item-new']"
        @click="task.resolved = !task.resolved"
        >
            <div :class="[task.resolved ? 'border-item-done' : 'border-item-new']"></div>
            <div 
                class="item-desc"
            >   
                <div
                  class="btn-task"
                  :class="[task.resolved ? 'btn-done' : 'btn-new']"
                  @click="deleteTask(task.id)"
                >
                    <img src="../img/close.svg" alt="X">
                </div>
                    <p :class="[task.resolved ? 'item-desc-done' : 'item-desc-new']">{{task.task}}</p>
            </div>
        </div>
</template>

<script>
    export default {
        name: 'TasksCard',
        props: ['tasksArray', 'task', 'deleteTask'],
    }
</script>

<style>
    @import url('../style/tasks.css');
</style>
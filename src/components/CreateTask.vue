<template>
    <div class="create-task-content">
        <input v-model="taskValue" type="text" placeholder="Nova tarefa..." >
        <button @click="resetInput(taskValue)">+</button>
    </div>
</template>

<script>

    export default {
        name: 'CreateTask',
        data() {
            return {
                taskValue: this.newTask,
            }
        },
        methods: {
            resetInput(task) {
                this.generateTask(task)
                this.taskValue = ''
            }
        },
        props: ['newTask', 'generateTask']
    }
</script>

<style>
    @import url('../style/create-task.css');
</style>
<script setup>
    import TasksCard from './TasksCard.vue';
</script>

<template>
    <div class="tasks-created-content">
        <ul v-for="(task, i) in tasksArray" :key="i">
            <li>
                <TasksCard :task="task"/>
            </li>
        </ul>
            
        {{ test() }}
    </div>
</template>

<script>


export default {
    name: 'Tasks',
    props: ['tasksArray'],
    methods: {
        test() {
            console.log('testando o retorno do array ===> ', this.tasksArray);
            
        }
    }
}


</script>

<style>
    @import url('../style/tasks.css');
</style>
<script setup>
    import TasksCard from './TasksCard.vue';
</script>

<template>
    <div class="tasks-created-content">
        <p v-if="tasksArray.length === 0">Sua vida está em dia! :)</p>
        <ul v-for="(task, i) in tasksArray" :key="i">
            <li>
                <TasksCard :task="task" :deleteTask="deleteTask"/>
            </li>
        </ul>            
    </div>
</template>

<script>


export default {
    name: 'Tasks',
    props: ['tasksArray', 'deleteTask'],
}


</script>

<style>
    @import url('../style/tasks.css');
</style>
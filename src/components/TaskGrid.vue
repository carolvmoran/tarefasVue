<template>
    <div class="task-grid">
        <template v-if="tasks.length">
            <Task v-for="(task, i) in tasks" :key="task.name" :task="task" @taskDeleted="$emit('taskDeleted', i)"></Task>
        </template>
        <p v-else class="no-task">Não há tarefas! <i class="fas fa-clipboard-check"></i></p>
    </div>
</template>
<script>
import Task from './Task.vue'
export default {
    components: { Task },
    props: {
        tasks: { type: Array, required: true}
    }
}
</script>
<style>
    .task-grid {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
    .task-grid .task {
        margin: 10px;
    }
    .no-task {
        color: #ffffff;
        font-size: 1.7rem;
        text-shadow: 2px 2px 2px black;
    }
</style>
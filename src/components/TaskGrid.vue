<template>
    <div class="tasks-grid">
        <template v-if="tasks.length">
            <Task v-for="(task, i) in tasks" :key="task.name"
                @taskDeleted="$emit('taskDeleted', i)"
                @taskStateChanged="$emit('taskStateChanged', i)"
                :task="task"></Task>
        </template>
        <p v-else class="no-tasks">Você não tem tarefas!</p>
    </div>
</template>

<script>
import Task from './Task.vue'

export default {
    components: {Task},
    props:{
        tasks: {type: Array, required: true}
    }
}
</script>

<style>
.tasks-grid{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    }
    .tasks-grid .task {
        margin: 10px;
    }
    .no-tasks{
        color: #AAA;
        font-size: 1.7rem;
    }
</style>
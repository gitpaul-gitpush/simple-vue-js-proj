<template>
    <div :key="task.id" v-for="task in tasks">
        <Task @delete-task="$emit('delete-task', task.id)" @toggle-reminder="$emit('toggle-reminder', task.id)" @collapse-details="setActive"  :task="task" :isActive="task.id === active" />
    </div>
    <i>**tasks highlighted in green are reminders</i>
</template>

<script>
import Task from './Task'

export default {
    name: 'Tasks',
    props: {
        tasks: Array
    },
    components: {
        Task
    },
    data() {
        return {
            active : -1
        }
    },
    emits: ['delete-task', 'toggle-reminder'],
    methods: {
        setActive(id) {
            this.active = id
        }
    },
    created() {
        this.active = -1;
    }
}
</script>
<template>
    <div :class="[task.reminder ? 'reminder' : '']" @click="collapseDetails(task.id)">
        <h3>
            <i :class="['fas', isActive ? 'fa-angle-up' : 'fa-angle-down']"></i> 
            {{ task.text }}
            <i @click="onDelete(task.id)" :style="{ color: 'red' }" class="fas fa-times"></i>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>


<script>
export default {
    name: 'Task',
    props: {
        task: Object,
        isActive: Boolean
    },
    methods: {
        onDelete(id) {
            this.$emit('delete-task', id)
        },
        collapseDetails(id) {
            this.$emit('collapse-details', id)
        }
    }
}

</script>

<style scope>
.reminder {
    background-color: lightgreen;
}

</style>
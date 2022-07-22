<template>
    <div :class="[task.reminder ? 'reminder' : '']" @dblclick="$emit('toggle-reminder', task.id)">
        <h3 @click="$emit('collapse-details', task.id)">
            <i :class="['fas', isActive ? 'fa-angle-up' : 'fa-angle-down']"></i> 
            {{ task.text }}
            <i @click="$emit('delete-task', task.id)" :style="{ color: 'red' }" class="fas fa-times"></i>
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

    }
}

</script>

<style scope>
.reminder {
    background-color: lightgreen;
}

</style>
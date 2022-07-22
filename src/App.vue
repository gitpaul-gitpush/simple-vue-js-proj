<template>
<div class="container">
    <Header title="Task Tracker"></Header>
    <Tasks @delete-task="deleteTask" @toggle-reminder="toggleReminder" :tasks="tasks" />
</div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'

export default {
    name: 'App',
    components: {
        Header,
        Tasks,
    },
    data() {
        return {
            tasks: [

            ]
        }
    },
    methods: {
        deleteTask(id) {
            if (confirm('Are you sure you want to delete this?')) {
                this.tasks = this.tasks.filter((task) => task.id !== id)
            }
            
        },
        toggleReminder(id) {
            this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task)
        }
    },
    created() {
        this.tasks = [
        {
            id: 1,
            text: 'Work 7am to 4pm',
            day: 'July 19, 2022 at 7:00am',
            reminder: false
        },
        {
            id: 2,
            text: 'Cook Dinner',
            day: 'July 19, 2022 at 5:30pm',
            reminder: true
        },
        {
            id: 3,
            text: 'Exercise',
            day: 'July 19, 2022 at 7:00pm',
            reminder: true
        }
    ];
  }
}
</script>

<style>

</style>
 
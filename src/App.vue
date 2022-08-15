<template>
<div class="container">
    <Header title="Task Tracker" @toggle-add-task="toggleAddTask" :isAddTaskOpen="showAddTask"></Header>
    <router-view :showAddTask="showAddTask">
    </router-view>
    <Footer> </Footer>
</div>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'

export default {
    name: 'App',
    components: {
    Header,
    Footer,
    Footer
},
    data() {
        return {
            showAddTask: false
        }
    },
    methods: {
        toggleAddTask() {
            this.showAddTask = !this.showAddTask
        }
    }
}
</script>

<style>

</style>
 
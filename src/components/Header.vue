<template>
    <header>
        <h1>{{ title }}</h1>
        <div>
        <Button v-show="homePage" :text="isAddTaskOpen ? 'Close': 'Add Task'" color="white" @btn-click="$emit('toggle-add-task')" />
        </div>
    </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: {
            type: String,
            default: 'Header',
        },
        isAddTaskOpen: Boolean
    },
    components: {
        Button
    },
    computed: {
        homePage() {
            if(this.$route.path === '/') {
                //home page
                return true
            }

            return false
        }
    }
}
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style> 
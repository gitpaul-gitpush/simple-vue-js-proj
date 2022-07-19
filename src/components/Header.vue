<template>
    <header>
        <h1>{{ title }}</h1>
        <div>
        <Button text="Add Task" color="white"/>
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
            default: 'Header'
        }
    },
    components: {
        Button
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
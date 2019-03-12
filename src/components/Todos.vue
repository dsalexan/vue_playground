<template>
    <div>
        <div :key="todo.id" v-for="todo in list">
            <h3>
                <todo-item v-bind:todo="todo" />
            </h3>
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
    name: 'Todos',
    components:{
        TodoItem
    },
    props: ['list']
}
</script>


<style scoped>

</style>

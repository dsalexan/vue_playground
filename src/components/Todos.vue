<template>
    <div>
        <div :key="todo.id" v-for="todo in list">
            <h3>
                <todo-item v-bind:todo="todo" @remove="$emit('remove', todo.id)" />
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
    h3{
        margin-block-end: 0px;
        margin-block-start: 0px;
    }
</style>

<template>
    <div 
    class="todo-item" 
    :class="{'is-complete':todo.completed}"
    :is_complete="{'true':todo.completed}">
        <p>
            <input type="checkbox" v-model="todo.completed"/>
            {{todo.title}}
            <button class="del" @click="$emit('remove', todo.id)">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ['todo']
}
</script>

<style lang="scss" scoped>
    .todo-item{
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete{
        text-decoration: line-through;
    }

    .del{
        background: rgb(196, 59, 59);
        color: white;
        float: right;
        border-radius: 50%;
        width: 22px;
        height: 22px;
        font-size: 14px;
        font-weight: 300;
        cursor: pointer;

        &:hover{
            background: red;
        }
    }
</style>


<template>
  <div id="app">
    <Header />
    <AddTodo @submit="addTodo"/>
    <Todos :list="todos" @remove="deleteTodo"/>
  </div>
</template>

<script>
import Header from './components/layout/Header'

import Todos from './components/Todos'
import AddTodo from './components/AddTodo'

export default {
  name: 'app',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data(){
    return {
      todos: [
        {
          id: 1,
          title: 'Title #1',
          completed: true
        },
        {
          id: 2,
          title: 'Title #2',
          completed: false
        },
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(t => t.id != id)
    },
    addTodo(todo){
      this.todos.push(todo)
    }
  }
}
</script>

<style lang="scss">
body{
  margin: 0px;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.btn{
  display: inline-block;
  border: none;
  background: #555;
  color: white;
  padding: 7px 20px;
  cursor: pointer;

  &:hover{
    background: #666;
  }
}
</style>

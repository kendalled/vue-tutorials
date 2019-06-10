<template>
  <div id="app">
    <Header msg="Welcome to your daily tasks"/>
  
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';
import Header from './components/layout/Header';

export default {
  name: 'app',
  components: {
    Todos,
    Header,
    AddTodo
    
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Take out trash",
          completed: false
        },

        {
          id: 2,
          title: "Get Laundry",
          completed: false
        },
        {
          id: 3,
          title: "Turn off Lights ",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id != id);
    },

    addTodo(newTodo) {
      if(newTodo.title != ''){
        this.todos = [...this.todos, newTodo];
      } else {
        alert('Title is empty!');
      }
      
    },

    
  }
}
</script>

<style>
body {
  padding-top: 0;
  margin-top: 0;
  background-color: #eee;
}


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
</style>

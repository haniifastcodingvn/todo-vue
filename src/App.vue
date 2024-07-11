<template>
  <h1 class="todo-title">todo</h1>
  <TodoApp msg="Welcome to Your Vue.js App"/>
</template>

<script>
import TodoApp from './components/TodoApp.vue';

export default {
  name: 'App',
  components: {
    TodoApp
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.todo-title {
  font-size: 60px;
  color: #f08080

}
</style>

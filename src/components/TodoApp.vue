<template>
  <div>
    <input class="input-todo" type="text" v-model="newTodo" placeholder="Add a new todo">
    <button class="todo-add" @click="addTodo">Add</button>

    <ul class="todo-list">
      <li v-for="(todo, index) in todos" :key="index" :class="flag ? 'todo-completed' : ''">
        <input class="input-tick" type="checkbox" @change="completedTodo($event)">
        <span>{{ todo }}</span>
        <button class="todo-delete" @click="deleteTodo(index)">x</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
      todos: [],
      flag: false
    };
  },

  methods: {
    addTodo() {
      if (this.newTodo.trim() !== '') {
        this.todos.push(this.newTodo);
        this.newTodo = '';
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
    completedTodo(e) {
      this.flag = e.target.checked;
    }
  }
};
</script>

<style>
  .input-todo {
    border: 1px solid #f08080;
    color: #000;
    height: 35px;
    width: 400px;
    padding: 5px 10px;
    font-size: 16px;

    &:focus {
      outline: 0;
      box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    }
  }

  .todo-add {
    margin-left: 20px;
    border: 1px solid #f08080;
    background-color: #fff;
    width: 100px;
    height: 40px;
    color: #f08080;
    transition: all .3s ease;
    cursor: pointer;

    &:hover {
      background-color: #f08080;
      border: 1px solid #fff;
      color: #fff;
    }
  }

  .todo-list {
    list-style-type: none;
    padding-left: 0;
    width: 530px;
    margin: 0 auto;
    text-align: left;
    margin-top: 30px;

    > li {
      padding-right: 30px;
      position: relative;
    }
  }

  .todo-delete {
    font-weight: 500;
    color: #f08080;
    background-color: transparent;
    border: 0;
    font-size: 20px;
    cursor: pointer;
    position: absolute;
    right: 0;
    top: -4px;
  }

  .todo-tick {
    width: 15px;
    height: 15px;
    border-radius: 100%;
    background-color: transparent;
    border: 1px solid #f08080;
    cursor: pointer;
  }

  .todo-completed {
    text-decoration: line-through;
  }

  .input-tick {
    width:15%;
    border: 5px solid #95bf47;
    border-radius: 5px;
  }
</style>

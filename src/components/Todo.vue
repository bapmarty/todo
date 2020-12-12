<template>
  <section class="todo-list">
    <input v-model="newTodo" v-on:keyup.enter="addTodo" placeholder="Add new todo">
    <ul>
      <li v-for="todo in todos" :key="todo.name">
        <div v-on:click="todo.completed = !todo.completed" :class="{completed: todo.completed}">
          {{ todo.name }}
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      todos: [
      ],
      newTodo: ''
    }
  },
  methods: {
    addTodo () {
      if (this.newTodo.length < 3) return ;
      this.todos.push({ name: this.newTodo, completed: false });
      this.newTodo = ''
    }
  }
}
</script>

<style lang="scss">
  .todo-list {
    display: block;
    width: 300px;
    background-color: none;
    input {
      width: calc(100% - 4px);
      background: none;
      border: 0;
      border-bottom: 2px solid #EEE;
      outline: none;
      color: #EEE;
      font-size: 1.2rem;
      font-family: Avenir;
      font-weight: 600;
      &::placeholder {
        color: #EEE;
        font-family: Avenir;
        font-weight: 400;
        font-size: 1.2rem;
      }
    }
    ul {
      list-style-type: none;
      margin: 5px 0;
      padding: 0;
      li {
        margin: 5px 0;
        padding: 0;
        color: #EEEA;
        font-weight: 600;
        border-bottom: 1px solid #EEEA;
        div {
          &.completed {
            text-decoration: line-through;
          }
        }
      }
    }
  }
</style>
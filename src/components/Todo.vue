<template>
  <section>
    <input v-model="newTodo" v-on:keyup.enter="addTodo" placeholder="Add new todo">
    <button v-on:click="addTodo">Submit</button>
    <ul>
      <li v-for="todo in todos" :key="todo.name">{{ todo.name }}</li>
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
      this.todos.push({ name: this.newTodo, completed: false });
      this.newTodo = ''
    }
  }
}
</script>
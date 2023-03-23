<script>
import TodoItem from './components/TodoItem.vue'

export default {
  components: { TodoItem },
  data() {
    return {
      newTodoText: '',
      todos: [],
      nextTodoId: 1
    }
  },
  methods: {
    addNewTodo() {
      this.todos.push({
        id: this.nextTodoId++,
        title: this.newTodoText
      })
      this.newTodoText = ''
    }
  }
}
</script>

<template>
  <div class="container mt-5">
    <form class="mb-3" @submit.prevent="addNewTodo">
      <div class="form-group">
        <div class="input-group">
          <input v-model="newTodoText" class="form-control" placeholder="Añade To Do...">
          <div class="input-group-append">
            <button class="btn btn-primary">Añadir</button>
          </div>
        </div>
      </div>
    </form>
    <ul class="list-group">
      <todo-item v-for="todo in todos" :key="todo.id" :title="todo.title" @remove="todos.splice(index, 1)"></todo-item>
    </ul>
  </div>
</template>

<template>
  <div class="todo-list">
    <li v-for="todo in this.todos" :key="todo">
      <button @click="removeTodo(todo)">remove</button>
      {{ todo.content }}
    </li>
    <TodoInput @add="addTodo"></TodoInput>
  </div>
</template>

<script lang='ts'>
import { defineComponent } from "vue";
import TodoInput from "./TodoInput.vue";
import ToDo from "../type/Todo";

export default defineComponent({
  components: {
    TodoInput,
  },

  data() {
    const todos: ToDo[] = [];
    let counter = 0;
    return { todos, counter };
  },

  methods: {
    addTodo(todoContent: string) {
      // count
      this.counter++;
      // add todo
      this.todos.push({ id: this.counter, content: todoContent });
    },
    removeTodo(todo: ToDo) {
      const index = this.todos.indexOf(todo);
      this.todos.splice(index, 1);
    },
  },
});
</script>

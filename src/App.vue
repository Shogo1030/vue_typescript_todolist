<template>
  <div class="todolistmain">
    <!--todo list-->
    <h1>todolist</h1>
    <TodoList></TodoList>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TodoList from "./components/TodoList.vue";

export default defineComponent({
  components: {
    TodoList,
  },
});
</script>

<style>
</style>

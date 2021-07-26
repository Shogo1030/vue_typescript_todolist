<template>
  <div class="todo-input">
    <input type="text" placeholder="add Todo" v-model="this.inputValue" />
    <button @click="onClick()">add</button>
  </div>
</template>

<script lang = 'ts'>
import { defineComponent, ref } from "vue";

export default defineComponent({
  data() {
    const inputValue = "";
    return { inputValue };
  },
  // function on click
  methods: {
    onClick() {
      this.$emit("add", this.inputValue);
      // reset input Value
      this.inputValue = "";
    },
    //alert("pushed");
  },
});
</script>

<template>
  <div class="todoWrapper">
    <input
      type="checkbox"
      v-on:change="toggle(todo);"
      v-bind:checked="todo.done"
    />

    <del v-if="todo.done"> {{ todo.text }} </del>
    <span v-else> {{ todo.text }} </span>
    <button class="removeTodo" v-on:click="removeTodo">remove</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],

  methods: {
    removeTodo() {
      this.$emit("todo:remove", this.todo.id);
    },
    toggle: function(todo) {
      todo.done = !todo.done;
    }
  }
};
</script>
<style></style>

<style src="../static/todoItem.css"></style>

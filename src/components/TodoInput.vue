<template>
  <div class="inputWrapper">
    <input type="text" v-model="text" />
    <button class="btn btn-primary" v-on:click="addTodo">Submit</button>
  </div>
</template>

<script>
export default {
  name: "TodoInput",
  data() {
    return {
      text: ""
    };
  },
  methods: {
    addTodo() {
      this.$emit("todo:add", this.text);
      this.text = "";
    }
  }
};
</script>

<style src="../static/todoInput.css"></style>

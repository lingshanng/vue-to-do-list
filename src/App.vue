<template>
  <div class="app">
    <div class="todo-wrapper">
      <AppHeader></AppHeader> <TodoInput v-on:todo:add="addTodo"></TodoInput>
      <TodoItem
        v-for="todo in todos"
        v-bind:todo="todo"
        v-on:todo:remove="removeTodo"
        :key="todo.id"
      ></TodoItem>
    </div>
  </div>
</template>

<script src="./app.js"></script>
<style src="./static/app.css"></style>

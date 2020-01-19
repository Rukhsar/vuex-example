<template>
  <div class="container" id="app">
    <div class="row">
      <FilterTodos />
      <AddTodo />
    </div>
    <Todos />
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo.vue";
import FilterTodos from "./components/FilterTodos.vue";

export default {
  name: "app",
  components: {
    Todos,
    AddTodo,
    FilterTodos
  }
};
</script>

<style>
#app {
  margin-top: 40px;
  font-family: "Open Sans", sans-serif;
}
</style>

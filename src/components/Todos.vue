<template>
  <div class="mt-5">
    <h3>Todos</h3>
    <p class="text-danger">Double click to mark a todo as completed.</p>
    <div class="row">
      <div class="col-md-4" v-for="todo in allTodos" :key="todo.id">
        <div class="card mt-4" style="width: 18rem;" @dblclick="onDblClick(todo)">
          <div class="card-body">
            <h5
              class="card-title"
              v-bind:class="{ 'text-success': todo.completed }"
            >{{ todo.title }}</h5>
            <a href="#" class="card-link float-right text-danger" @click="deleteTodo(todo.id)">
              <i class="fa fa-trash"></i>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "Todos",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDblClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      };
      this.updateTodo(updTodo);
    }
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  }
};
</script>
<style>
</style>

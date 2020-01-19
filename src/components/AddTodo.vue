<template>
  <div class="col-md-8">
    <div class="card mt-4">
      <div class="card-body">
        <h5 class="card-title">Add Todo</h5>
        <div class="card-text">
          <form @submit="onSubmit">
            <div class="form-group">
              <input type="text" class="form-control w-75" v-model="title" placeholder="add todo" />
            </div>
            <button type="submit" class="btn btn-success float-right">Save Todo</button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "AddTodo",
  date() {
    return {
      title: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    }
  }
};
</script>

<style scoped>
</style>

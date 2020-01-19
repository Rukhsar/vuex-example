<template>
  <div class="col-md-4">
    <div class="card mt-4">
      <div class="card-body">
        <h5 class="card-title">Filter Todos</h5>
        <div class="card-text">
          <select class="form-control" @change="filterTodos($event)">
            <option value="200">200</option>
            <option value="100">100</option>
            <option value="50">50</option>
            <option value="20">20</option>
            <option value="10">10</option>
            <option value="5">5</option>
          </select>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "FilterTodos",
  methods: mapActions(["filterTodos"])
};
</script>

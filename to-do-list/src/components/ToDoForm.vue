<template>
  <form class="row g-1">
    <div class="col-9">
      <input
        type="text"
        class="form-control"
        id="newTask"
        placeholder="Add New Task..."
      />
    </div>
    <div class="col">
      <button type="submit" class="btn btn-primary">+</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "ToDoForm",
};
</script>

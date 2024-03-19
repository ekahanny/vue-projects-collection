<template>
  <form class="d-flex justify-content-center align-items-center mb-4">
    <div class="form-outline flex-fill">
      <input
        type="text"
        id="addTask"
        class="form-control"
        placeholder="Add New Task..."
        required
      />
    </div>
    <button type="submit" class="btn btn-info ms-2">+</button>
  </form>
</template>

<script>
export default {
  name: "ToDoForm",
};
</script>

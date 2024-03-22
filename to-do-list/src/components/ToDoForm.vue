<template>
  <form
    class="d-flex justify-content-center align-items-center mb-4"
    @submit.prevent="submit"
  >
    <div class="form-outline flex-fill">
      <input
        type="text"
        id="addTask"
        class="form-control"
        placeholder="Add New Task..."
        required
        v-model="task"
      />
    </div>
    <button type="submit" class="btn btn-info ms-2">+</button>
  </form>
</template>

<script>
export default {
  name: "ToDoForm",
  data() {
    return {
      task: "",
    };
  },
  methods: {
    submit: function () {
      this.emitToDo();
    },
    // method utk memanggil emit bernama newToDo
    emitToDo: function () {
      this.$emit("newToDo", {
        task: this.task,
        id: `$todo_${Math.random() * 1000}`,
        isCompleted: false,
      });
    },
  },
};
</script>

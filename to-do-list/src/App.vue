<template>
  <h1 class="mt-5">TO DO LIST</h1>
  <ToDoForm></ToDoForm>
</template>

<script>
import ToDoForm from "./components/ToDoForm.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    ToDoForm,
  },
};
</script>

<style>
body {
  min-height: 100vh;
  display: flex;
  justify-content: center;
}

h1 {
  font-family: "Newsreader", serif;
}
</style>

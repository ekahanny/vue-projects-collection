<template>
  <div class="container h-100">
    <div class="row d-flex justify-content-center align-items-center h-100">
      <div class="col col-xl-10">
        <div class="card">
          <div class="card-body p-5">
            <h1 class="text-center">TO DO LIST</h1>
            <!-- menjalankan event/emit -->
            <ToDoForm @newToDo="handleNewToDo" />
            <ActiveList
              v-for="todo in todoList"
              :key="todo.id"
              :todo="todo"
              @onToggleIsCompleted="handleToggleIsChecked"
            ></ActiveList>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ToDoForm from "./components/ToDoForm.vue";
import ActiveList from "./components/ActiveList.vue";

export default {
  name: "App",
  components: {
    ToDoForm,
    ActiveList,
  },
  data() {
    return {
      todoList: [],
    };
  },
  methods: {
    // method yang akan dijalankan ketika emit newToDo berlangsung
    handleNewToDo: function (ToDo) {
      this.todoList.push(ToDo);
    },
    handleToggleIsChecked: function ({ value, id }) {
      console.log(value, id);
      const todo = this.findTodo(id);
      todo.isCompleted = value;

      console.log(this.todoList);
    },
    findTodo(id) {
      return this.todoList.find((todo) => todo.id === id);
    },
  },
};
</script>

<style>
h1 {
  font-family: "Newsreader", serif;
}
</style>

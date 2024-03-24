<template>
  <div class="container h-100">
    <div class="row d-flex justify-content-center align-items-center h-100">
      <div class="col col-xl-10">
        <div class="card my-4">
          <div class="card-body pt-5 px-5 pb-2">
            <h1 class="text-center">Simple Form</h1>
            <FormData />
          </div>
        </div>

        <div class="card">
          <div class="card-body p-5">
            <FormResult />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FormData from "./components/FormData.vue";
import FormResult from "./components/FormResult.vue";

export default {
  name: "App",
  components: {
    FormData,
    FormResult,
  },
};
</script>

<style>
h1 {
  font-family: "Newsreader", serif;
}
</style>

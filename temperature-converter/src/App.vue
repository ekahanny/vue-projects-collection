<template>
  <div class="container h-100">
    <div class="row d-flex justify-content-center align-items-center h-100">
      <!-- Image -->
      <div class="col-md-3">
        <img
          alt="temperature"
          src="./assets/temperature.png"
          width="550"
          height="auto"
          class="img-fluid"
        />
      </div>

      <!-- Form Input -->
      <div class="col-md-9">
        <div class="card border border-warning">
          <div class="card-body py-4">
            <CardComponent />
          </div>
        </div>

        <!-- Card "Result" -->
        <div class="card border border-warning mt-3 w-100">
          <div class="card-body py-4">
            <p class="ps-4">Result</p>
            <p class="ps-4">0 C</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CardComponent from "./components/CardComponent.vue";
export default {
  name: "App",
  components: {
    CardComponent,
  },
};
</script>

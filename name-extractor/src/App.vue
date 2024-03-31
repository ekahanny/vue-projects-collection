<template>
  <div class="container mt-5">
    <h1 class="text-center">Name Extractor</h1>
    <p class="text-center">
      Name Etractor adalah program pengekstrak nama otomatis
    </p>
    <InputUser />
    <br />
    <NameResult />
  </div>
</template>

<script>
import InputUser from "./components/InputUser.vue";
import NameResult from "./components/NameResult.vue";
export default {
  name: "App",
  components: {
    InputUser,
    NameResult,
  },
};
</script>

<style></style>

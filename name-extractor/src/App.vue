<template>
  <div class="container mt-5">
    <h1 class="text-center">Name Extractor</h1>
    <p class="text-center">
      Name Etractor adalah program pengekstrak nama otomatis
    </p>
    <InputUser @emitSubmitForm="handleSubmitForm" />
    <br />
    <NameResult :userData="nameOfUsers" />
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
  data() {
    return {
      nameOfUsers: {
        firstName: "",
        middleName: "",
        lastName: "",
      },
    };
  },
  methods: {
    handleSubmitForm: function (inputNama) {
      console.log(inputNama);
      this.nameOfUsers.firstName = inputNama.firstName;
      this.nameOfUsers.middleName = inputNama.middleName;
      this.nameOfUsers.lastName = inputNama.lastName;
    },
  },
};
</script>

<style></style>

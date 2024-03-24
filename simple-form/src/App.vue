<template>
  <div class="container h-100">
    <div class="row d-flex justify-content-center align-items-center h-100">
      <div class="col col-xl-10">
        <div class="card my-4">
          <div class="card-body pt-5 px-5 pb-2">
            <h1 class="text-center">Simple Form</h1>
            <!-- Step 5 : Menginisiasi emit yang telah dibuat pada component sebelumnya -->
            <FormData @emitSubmitForm="handleSubmitForm" />
          </div>
        </div>

        <div class="card">
          <div class="card-body p-5">
            <!-- Step 8 : Mengirim formData menuju component FormResult untuk ditampilkan -->
            <FormResult :formData="formData" />
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
  /* Step 6 : Menginisiasi formData untuk menyimpan data
    yg akan dipassing dari component sebelumnya (FormData)
    menuju component selanjutnya (FormResult) */
  data() {
    return {
      formData: {},
    };
  },
  methods: {
    /* Step 7 : Membuat method yang akan dijalankan ketika
       emit berlangsung, data dari emit tsb akan disimpan
       kedalam property formData */
    handleSubmitForm: function (formData) {
      this.formData = formData;
    },
  },
};
</script>

<style>
h1 {
  font-family: "Newsreader", serif;
}
</style>

<template>
  <!-- Step 3 : Membuat sebuah event yang akan menjalankan sebuah method -->
  <form
    @submit.prevent="submit"
    class="d-flex justify-content-center align-items-center mb-4"
  >
    <div class="form-outline flex-fill mt-3">
      <label for="name" class="form-label"
        >Nama Lengkap <span class="text-danger">*</span></label
      >
      <!-- Step 1 : Mengambil inputan dari user menggunakan v-model -->
      <input
        type="text"
        id="name"
        class="form-control mb-3 border border-secondary"
        required
        v-model="nama"
      />
      <label for="nim" class="form-label"
        >NIM <span class="text-danger">*</span></label
      >
      <input
        type="text"
        id="nim"
        class="form-control mb-3 border border-secondary"
        required
        v-model="nim"
      />
      <label for="fakultas" class="form-label"
        >Fakultas <span class="text-danger">*</span></label
      >
      <input
        type="text"
        id="fakultas"
        class="form-control mb-3 border border-secondary"
        required
        v-model="fakultas"
      />
      <label for="prodi" class="form-label"
        >Program Studi <span class="text-danger">*</span></label
      >
      <input
        type="text"
        id="prodi"
        class="form-control mb-3 border border-secondary"
        required
        v-model="prodi"
      />
      <div class="d-flex justify-content-center">
        <button type="submit" class="btn btn-info mt-3">Submit</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "FormData",
  // Step 2 : Menginisiasi data yg akan digunakan, diambil dari v-model
  data() {
    return {
      nama: "",
      nim: "",
      fakultas: "",
      prodi: "",
    };
  },
  methods: {
    // Step 4 : Membuat method yang akan menjalankan emit berisi data yg akan digunakan
    submit: function () {
      this.$emit("emitSubmitForm", {
        nama: this.nama,
        nim: this.nim,
        fakultas: this.fakultas,
        prodi: this.prodi,
      });
      this.nama = "";
      this.nim = "";
      this.fakultas = "";
      this.prodi = "";
    },
  },
};
</script>

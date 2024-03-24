<template>
  <div class="d-flex justify-content-center align-items-center mb-4">
    <h1 class="text-center">Data Mahasiswa</h1>
  </div>
  <div>
    <hr />
    <!-- Step 10 : Menampilkan data yang diambil dari props, data berasal dari parent components -->
    <h4 class="p-2">Nama Lengkap : {{ formData.nama }}</h4>
    <h4 class="p-2">NIM : {{ formData.nim }}</h4>
    <h4 class="p-2">Fakultas : {{ formData.fakultas }}</h4>
    <h4 class="p-2">Program Studi : {{ formData.prodi }}</h4>
    <hr />
  </div>
</template>

<script>
export default {
  name: "FormResult",
  // Step 9 : Membuat props formData untuk menerima data dari App.vue
  props: {
    formData: Object,
  },
};
</script>

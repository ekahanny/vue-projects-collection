<template>
  <h2 class="alert alert-success text-center">
    Selamat Datang {{ userData.firstName }}, Senang Anda Dapat Bergabung!
  </h2>
  <b class="text-warning badge badge-dark"> Hasil Ekstrak Nama Anda : </b>
  <br />
  <br />
  <div class="rounded border border-danger p-2">
    <p>Nama Depan : {{ userData.firstName }}</p>
    <p>Nama Tengah : {{ userData.middleName }}</p>
    <p>Nama Akhir : {{ userData.lastName }}</p>
  </div>
</template>

<script>
export default {
  name: "NameResult",
  props: {
    userData: Object,
  },
};
</script>

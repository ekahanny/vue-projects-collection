<template>
  <div class="counter">
    <input type="text" class="input-box" placeholder="0" v-model="number" />
    <button class="start" @click="generateNumber">Take Your Guess!</button>
  </div>
  <div class="hasil">
    <div>Hasil</div>
    <div class="list">
      <div class="item">Status: {{ status }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      number: 0,
      status: "", // Menambahkan properti status
    };
  },
  methods: {
    generateNumber: function () {
      let randomNumber = Math.floor(Math.random() * 100);
      if (this.number > randomNumber) {
        this.status = "Tebakanmu terlalu besar!"; // Mengatur status tebakan
      } else if (this.number < randomNumber) {
        this.status = "Tebakanmu terlalu kecil!"; // Mengatur status tebakan
      } else if (this.number === randomNumber) {
        this.status = "Tebakanmu benar!"; // Mengatur status tebakan
      }

      setTimeout(() => {
        this.status = "";
      }, 2000);
    },
  },
};
</script>

<style>
@import "./assets/css/style.css";
</style>

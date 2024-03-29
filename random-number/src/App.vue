<template>
  <div class="counter">
    <input type="text" class="input-box" placeholder="0" v-model="number" />
    <button class="start" @click="generateNumber">Take Your Guess!</button>
  </div>
  <div class="hasil">
    <div>Hasil</div>
    <div class="list">
      <div class="item">Hasil : {{ number }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      number: 0,
    };
  },
  methods: {
    generateNumber: function () {
      let randomNumber = Math.floor(Math.random() * 100);
      this.number = randomNumber;
    },
  },
};
</script>

<style>
@import "./assets/css/style.css";
</style>

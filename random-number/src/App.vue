<template>
  <div class="counter">
    <input type="text" class="input-box" placeholder="0" v-model="number" />
    <button class="start" @click="generateNumber" :disabled="isCounting">
      Take Your Guess!
    </button>
  </div>
  <div class="hasil">
    <div>Hasil</div>
    <div class="list">
      <div class="item" v-for="(num, index) in randomNumber" :key="index">
        Hasil : {{ num }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      isCounting: false,
      number: 0,
      randomNumber: [],
    };
  },
  methods: {
    generateNumber: function () {
      if (this.isCounting) {
        return;
      }

      let counter = 0;
      this.isCounting = true;

      let instance = setInterval(() => {
        this.number = Math.floor(Math.random() * 100) + 1;
        counter++;

        if (counter >= 10) {
          this.randomNumber.push(this.number);
          clearInterval(instance);
          this.isCounting = false;
        }
      }, 50);
    },
  },
};
</script>

<style>
@import "./assets/css/style.css";
</style>

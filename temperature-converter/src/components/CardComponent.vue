<template>
  <div class="row d-flex justify-content-center align-items-center">
    <div class="col-md-5">
      <div class="form-group">
        <label for="suhu" class="mb-2">Suhu:</label>
        <input
          type="number"
          class="form-control border border-danger"
          id="suhu"
          placeholder="Masukkan suhu"
          v-model="suhu"
          required
        />
      </div>
    </div>
    <div class="col-md-5">
      <div class="form-group">
        <label for="tipe" class="mb-2">Tipe:</label>
        <select
          class="form-select border border-danger"
          id="tipe"
          v-model="selectedType"
        >
          <option :value="null" selected disabled>Pilih Satuan Suhu...</option>
          <option value="celcius">Celcius</option>
          <option value="fahrenheit">Fahrenheit</option>
          <option value="kelvin">Kelvin</option>
        </select>
      </div>
    </div>
    <div class="col-md-auto">
      <div class="form-group">
        <label for="submit">&nbsp;</label>
        <button class="btn btn-danger form-control" @click="submit">
          Submit
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  data() {
    return {
      suhu: null,
      selectedType: "",
    };
  },
  methods: {
    submit: function () {
      this.$emit("emitSubmit", {
        type: this.selectedType,
        suhu: this.suhu,
      });
    },
  },
  computed: {
    formattedSuhu: function () {
      if (this.suhu === "celcius") {
        return this.suhu + "°C";
      } else if (this.suhu === "farenheit") {
        return this.suhu + "F";
      } else {
        return this.suhu + "K";
      }
    },
  },
};
</script>

<template>
  <div class="container h-100">
    <div class="row d-flex justify-content-center align-items-center h-100">
      <h1 class="d-flex justify-content-center align-items-center">
        Temperature Converter
      </h1>
      <div class="col-md-3">
        <img
          alt="temperature"
          src="./assets/temperature.png"
          width="550"
          height="auto"
          class="img-fluid"
        />
      </div>

      <div class="col-md-9">
        <div class="card border border-warning">
          <div class="card-body py-4">
            <CardComponent @emitSubmit="handleEmitSubmit" />
          </div>
        </div>

        <div class="card border border-warning mt-3 w-100">
          <div class="card-body py-4">
            <p class="ps-4">Result</p>
            <p v-if="dataForm.hasilKonversi" class="ps-4">
              {{ dataForm.hasilKonversi }} {{ satuan }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CardComponent from "./components/CardComponent.vue";

export default {
  name: "App",
  components: {
    CardComponent,
  },
  data() {
    return {
      dataForm: {},
    };
  },
  methods: {
    handleEmitSubmit: function (dataForm) {
      this.dataForm = dataForm;
      let suhu = dataForm.suhu;
      let convertFrom = dataForm.convertFrom;
      let convertTo = dataForm.convertTo;

      const hasilKonversi = this.convert(suhu, convertFrom, convertTo);
      this.dataForm.hasilKonversi = hasilKonversi;

      console.log(dataForm);
    },
    convert: function (suhu, convertFrom, convertTo) {
      let hasil = 0;
      let satuan = "";
      switch (convertFrom) {
        case "celcius":
          if (convertTo === "fahrenheit") {
            hasil = (suhu * 9) / 5 + 32;
            satuan = " °F";
          } else if (convertTo === "kelvin") {
            hasil = suhu + 273.15;
            satuan = " K";
          } else if (convertTo === "celcius") {
            hasil = suhu;
            satuan = " °C";
          }
          break;
        case "fahrenheit":
          if (convertTo === "celcius") {
            hasil = ((suhu - 32) * 5) / 9;
            satuan = " °C";
          } else if (convertTo === "kelvin") {
            hasil = ((suhu - 32) * 5) / 9 + 273.15;
            satuan = " K";
          } else if (convertTo === "fahrenheit") {
            hasil = suhu;
            satuan = " °F";
          }
          break;
        case "kelvin":
          if (convertTo === "celcius") {
            hasil = suhu - 273.15;
            satuan = " °C";
          } else if (convertTo === "fahrenheit") {
            hasil = ((suhu - 273.15) * 9) / 5 + 32;
            satuan = " °F";
          } else if (convertTo === "kelvin") {
            hasil = suhu;
            satuan = " K";
          }
          break;
        default:
          return "Invalid unit";
      }
      return hasil.toFixed(2) + satuan;
    },
  },
};
</script>

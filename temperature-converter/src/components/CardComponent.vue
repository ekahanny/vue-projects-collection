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
        />
      </div>
    </div>
    <div class="col-md-5">
      <div class="form-group">
        <label for="tipe" class="mb-2">Tipe:</label>
        <select class="form-select border border-danger" id="tipe">
          <option value="" selected disabled>Pilih Satuan Suhu...</option>
          <option value="celcius">Celcius</option>
          <option value="fahrenheit">Fahrenheit</option>
          <option value="kelvin">Kelvin</option>
        </select>
      </div>
    </div>
    <div class="col-md-auto">
      <div class="form-group">
        <label for="submit">&nbsp;</label>
        <button class="btn btn-danger form-control">Submit</button>
      </div>
    </div>
  </div>
</template>

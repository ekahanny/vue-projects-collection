<template>
  <form class="d-flex justify-content-center align-items-center mb-4">
    <div class="form-outline flex-fill mt-3">
      <label for="name" class="form-label"
        >Nama Lengkap <span class="text-danger">*</span></label
      >
      <input
        type="text"
        id="name"
        class="form-control mb-3 border border-secondary"
        required
      />
      <label for="nim" class="form-label"
        >NIM <span class="text-danger">*</span></label
      >
      <input
        type="text"
        id="nim"
        class="form-control mb-3 border border-secondary"
        required
      />
      <label for="fakultas" class="form-label"
        >Fakultas <span class="text-danger">*</span></label
      >
      <input
        type="text"
        id="fakultas"
        class="form-control mb-3 border border-secondary"
        required
      />
      <label for="prodi" class="form-label"
        >Program Studi <span class="text-danger">*</span></label
      >
      <input
        type="text"
        id="prodi"
        class="form-control mb-3 border border-secondary"
        required
      />
      <div class="d-flex justify-content-center">
        <button type="submit" class="btn btn-info mt-3">Submit</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {};
</script>

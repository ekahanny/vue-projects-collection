<template>
  <div class="input-group">
    <input
      class="form-control"
      type="text"
      placeholder="Ketik Nama Lengkap..."
      v-model="inputNama.nama"
      @keypress.enter="submit"
    />
    <button class="btn btn-primary" @click="submit">SUBMIT</button>
  </div>
</template>

<script>
export default {
  name: "InputUser",
  data() {
    return {
      inputNama: {
        firstName: "",
        middleName: "",
        lastName: "",
      },
    };
  },
  methods: {
    submit: function () {
      let fullName = this.inputNama.nama.split(" ");
      this.inputNama.firstName = fullName.shift();
      this.inputNama.lastName = fullName.pop();
      this.inputNama.middleName = fullName.join(" ");

      this.$emit("emitSubmitForm", this.inputNama);

      this.inputNama.nama = "";
    },
  },
};
</script>

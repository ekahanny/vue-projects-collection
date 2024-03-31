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
      this.inputNama.firstName = fullName[0];
      for (let i = 1; i < fullName.length - 1; i++) {
        this.inputNama.middleName += fullName[i] + " ";
      }
      this.inputNama.lastName = fullName[fullName.length - 1];

      this.$emit("emitSubmitForm", this.inputNama);
    },
  },
};
</script>

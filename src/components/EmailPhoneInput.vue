<template>
  <div class="wrapper">
    <input ref="mask" type="text" @keydown="keydown">
  </div>
</template>

<script>
import IMask from "imask";

export default {
  name: "EmailPhoneInput",
  mounted() {
    this.masks = {
      phone: '+7 (000) 000-00-00',
      email: /^\w+|@$/
    }
    let options = {
      mask: this.masks.phone,
    }
    this.mask = IMask(this.$refs.mask, options);
  },
  methods: {
    keydown: function (event) {
      let key = event.keyCode;
      if (key >= 48 && key < 57 && !event.shiftKey && this.mask.unmaskedValue.search(/^[0-9]+$/) >= 0) {
        this.mask.updateOptions({mask: this.masks.phone})
      }
      if ((event.key.length === 1 && event.key.search(/[a-zA-Z]/) >= 0) || (key === 50 && event.shiftKey)) {
        this.mask.updateOptions({mask: this.masks.email})
      }
    },
  }
}
</script>

<style scoped>

</style>
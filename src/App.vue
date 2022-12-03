<template>
  <main>
    <EmailPhoneInput />
  </main>
</template>

<script>
import EmailPhoneInput from "@/components/EmailPhoneInput";
export default {
  name: 'App',
  components: {EmailPhoneInput}
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: content-box;
}
main {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>

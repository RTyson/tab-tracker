<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h1>Register</h1>
    <input type="text" v-model="regEmail" name="email" placeholder="email">
    <br>
    <input type="password" v-model="regPwd" name="password" placeholder="password">
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script setup>
import AuthenticaionService from '../services/AuthenticationService'
import { ref } from 'vue'

const regEmail = ref("");
const regPwd = ref("");

const register = async () => {
  const response = await AuthenticaionService.register({
    email: regEmail.value,
    password: regPwd.value
  })
  console.log(response.data)
}
</script>

<style lang="scss" scoped></style>
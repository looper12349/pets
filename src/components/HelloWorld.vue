<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>Welcome to your Vue 3 + Vite app!</p>
    <button ><router-link to="/login">Login</router-link></button>
  </div>
</template>

<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<style scoped>
.hello {
  text-align: center;
}
</style>
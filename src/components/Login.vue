<template>
    <section class="adminloginSection">
      <div class="container-fluid">
        <div class="row">
          <div class="loginBox">
            <div class="loginBoxInnerForm">
              <form @submit.prevent="handleSubmit">
                <div class="form-group">
                  <label for="exampleInputEmail1">User ID</label>
                  <input v-model="username" type="text" class="form-control" id="exampleInputEmail1" placeholder="">
                  <span class="errorform">{{ usernameError }}</span>
                </div>
                <div class="form-group">
                  <label for="exampleInputPassword1">Password</label>
                  <input v-model="password" type="password" class="form-control" id="exampleInputPassword1" placeholder="">
                  <span class="errorform">{{ passwordError }}</span>
                </div>
                <button type="submit" class="btn btn-default">LOGIN</button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { useRouter } from 'vue-router'
  
  const router = useRouter()
  const username = ref('')
  const password = ref('')
  const usernameError = ref('')
  const passwordError = ref('')
  
  const handleSubmit = () => {
    // Reset error messages
    usernameError.value = ''
    passwordError.value = ''
  
    // Basic validation
    if (!username.value) {
      usernameError.value = 'Username is required'
    }
    if (!password.value) {
      passwordError.value = 'Password is required'
    }
  
    // If no errors, proceed with login logic
    if (username.value && password.value) {
      console.log('Login attempt', { username: username.value, password: password.value })
      alert('Login attempt', { username: username.value, password: password.value })
      // Here you would typically make an API call to authenticate the user
      // For now, we'll just log to the console and redirect to home
      router.push('/')
    }
  }
  </script>
  
  <style scoped>
  /* You can add your styles here */
  .errorform {
    color: red;
  }
  </style>
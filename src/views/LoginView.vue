<script setup>
  import { RouterLink,useRouter } from 'vue-router'
  import { ref } from 'vue'

  const router = useRouter()

  const handleSubmit=() =>{
    console.log(`Username: ${username.value}, Password: ${password.value}`);
  }

  const backToRegister = () => {
    router.push({name: 'register' })
  }

</script>

<template>
  <div class="login-container">
    <h2>Login</h2>
    <form>
      <div class="form-group">
        <label for="username">Username</label>
        <input type="text" name="ussername" id="username" required />
      </div>
      <div class="form-group">
        <label for="password">password</label>
        <input type="password" name="password" id="password" required />
      </div>
      <button @click="handleSubmit()">Submit</button>
    </form>
    <p>Don't have an account?<RouterLink to = "/register">Register here</RouterLink></p>
  </div>
</template>

<style>
  /* Container for the entire login page */
.login-container {
  max-width: 400px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
}
/* Box containing the login form */
.login-box {
  width: 100%;
  max-width: 400px;
  padding: 20px;
  background-color: #ffffff;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  text-align: center;
}

/* Header style */
.login-box h2 {
  margin-bottom: 20px;
  color: #333333;
}

/* Form group style */
.form-group {
  margin-bottom: 15px;
  text-align: left;
}

/* Label style */
.form-group label {
  display: block;
  margin-bottom: 5px;
  color: #666666;
}

/* Input style */
.form-group input {
  width: 100%;
  padding: 10px;
  border: 1px solid #cccccc;
  border-radius: 5px;
  box-sizing: border-box;
}

/* Button style */
button {
  width: 100%;
  padding: 10px;
  background-color: #007bff;
  color: #ffffff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #0056b3;
}

/* Link style */
p {
  margin-top: 15px;
}
</style>
<script setup>
import { ref } from 'vue'

const email = ref('');
const password = ref('');
const error = ref('');
const loggedIn = ref(false);

function handleLogin() {
  // The email must be gwynne@laurence
  if (
    email.value.trim().toLowerCase() === 'gwynne@laurence' &&
    password.value === 'LOVE'
  ) {
    loggedIn.value = true;
    error.value = '';
  } else {
    error.value = 'Incorrect email or password!';
  }
}
</script>

<template>
  <div v-if="!loggedIn" class="login-book">
    <div class="login-page">
      <h2>Login to Open the Book</h2>
      <form @submit.prevent="handleLogin">
        <label>Email (hint: yourname@partnername)</label>
        <input v-model="email" type="text" placeholder="gwynne@laurence" />
        <label>Password (hint: a feeling)</label>
        <input v-model="password" type="password" placeholder="Password" />
        <button type="submit">Open</button>
        <p v-if="error" class="error">{{ error }}</p>
      </form>
    </div>
  </div>
  <div v-else>
    <slot />
  </div>
</template>

<style scoped>
.login-book {
  width: 400px;
  margin: 60px auto 0 auto;
  background: #f9f6f2;
  border-radius: 12px;
  box-shadow: 0 4px 24px rgba(0,0,0,0.10);
  padding: 32px 24px;
  font-family: 'Georgia', serif;
}
.login-page {
  background: #fff;
  border-radius: 8px;
  padding: 24px 20px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
}
h2 {
  text-align: center;
  color: #b48a78;
  margin-bottom: 18px;
}
label {
  display: block;
  margin-top: 12px;
  font-size: 1em;
  color: #7a5c4d;
}
input {
  width: 100%;
  padding: 8px 10px;
  margin-top: 4px;
  border: 1px solid #e0d6cf;
  border-radius: 4px;
  font-size: 1em;
  margin-bottom: 10px;
  font-family: inherit;
}
button {
  width: 100%;
  padding: 10px;
  background: #b48a78;
  color: #fff;
  border: none;
  border-radius: 4px;
  font-size: 1.1em;
  cursor: pointer;
  margin-top: 10px;
  transition: background 0.2s;
}
button:hover {
  background: #a06c54;
}
.error {
  color: #d9534f;
  margin-top: 8px;
  text-align: center;
}
</style>

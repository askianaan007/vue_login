<script setup lang="ts">
import { ref } from "vue";

const email = ref("");
const password = ref("");
const errorMessage = ref("");

const handleLogin = () => {
  if (!email.value || !password.value) {
    errorMessage.value = "Please enter both email and password.";
    return;
  }
  alert(`Welcome back! \nEmail: ${email.value}`);
  email.value = "";
  password.value = "";
  errorMessage.value = "";
};
</script>

<template>
  <div class="flex justify-center items-center min-h-screen bg-gray-100">
    <div class="bg-white p-8 rounded-lg shadow-md w-96">
      <h2 class="text-2xl font-bold text-center text-gray-700 mb-6">Login</h2>

      <form @submit.prevent="handleLogin">
        <div class="mb-4">
          <label for="email" class="block text-gray-700 font-medium"
            >Email</label
          >
          <input
            id="email"
            type="email"
            v-model="email"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring focus:border-blue-300"
            placeholder="Enter your email"
          />
        </div>

        <div class="mb-4">
          <label for="password" class="block text-gray-700 font-medium"
            >Password</label
          >
          <input
            id="password"
            type="password"
            v-model="password"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring focus:border-blue-300"
            placeholder="Enter your password"
          />
        </div>
        <p v-if="errorMessage" class="text-red-500 text-sm mb-3">
          {{ errorMessage }}
        </p>
        <button
          type="submit"
          class="w-full bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600 transition"
        >
          Login
        </button>
      </form>
    </div>
  </div>
</template>

<style scoped></style>

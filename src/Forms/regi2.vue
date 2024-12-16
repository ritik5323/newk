<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="flex justify-center items-center min-h-screen bg-blue-300">
    <div class="w-full max-w-md sm:max-w-lg md:max-w-xl bg-white p-6 rounded-lg shadow-lg">
      <h3 class="text-2xl text-center mb-4">{{ isLogin ? "Login to Your Account" : "Create an Account" }}</h3>
      <form @submit.prevent="handleSubmit">
        <div v-if="!isLogin" class="mb-4 grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div>
            <label class="block text-sm font-bold text-gray-700">First Name</label>
            <input v-model="form.firstName" type="text" class="w-full p-2 border rounded" placeholder="First Name" />
          </div>
          <div>
            <label class="block text-sm font-bold text-gray-700">Last Name</label>
            <input v-model="form.lastName" type="text" class="w-full p-2 border rounded" placeholder="Last Name" />
          </div>
        </div>
        <div class="mb-4">
          <label class="block text-sm font-bold text-gray-700">Email</label>
          <input v-model="form.email" type="email" class="w-full p-2 border rounded" placeholder="Email" />
        </div>
        <div class="mb-4">
          <label class="block text-sm font-bold text-gray-700">Password</label>
          <input v-model="form.password" type="password" class="w-full p-2 border rounded" placeholder="********" />
        </div>
        <div v-if="!isLogin" class="mb-4">
          <label class="block text-sm font-bold text-gray-700">Confirm Password</label>
          <input v-model="form.confirmPassword" type="password" class="w-full p-2 border rounded" placeholder="********" />
        </div>
        <div class="mb-6">
          <button type="submit" class="w-full py-2 bg-blue-500 text-white rounded-full hover:bg-blue-700">{{ isLogin ? "Login" : "Register Account" }}</button>
        </div>
        <hr class="mb-6" />
        <div class="text-center">
          <a @click="toggleForm" class="text-sm text-blue-500 hover:text-blue-800 cursor-pointer">
            {{ isLogin ? "Don't have an account? Register!" : "Already have an account? Login!" }}
          </a>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { reactive, ref } from "vue";

const form = reactive({
  firstName: "",
  lastName: "",
  email: "",
  password: "",
  confirmPassword: "",
});

const isLogin = ref(true);

const handleSubmit = () => {
  if (isLogin.value) {
    if (!form.email || !form.password) {
      alert("Please enter both email and password.");
      return;
    }
    alert("Logged in successfully!");
  } else {
    if (!form.firstName || !form.lastName || !form.email || !form.password || !form.confirmPassword) {
      alert("All fields are required for registration.");
      return;
    }
    if (form.password !== form.confirmPassword) {
      alert("Passwords do not match!");
      return;
    }
    alert("Registration successful!");
  }
};

// const toggleForm = () => {
//   isLogin.value = !isLogin.value;
//   Object.keys(form).forEach(key => form[key] = "");
// };

const toggleForm = () => {
  isLogin.value = !isLogin.value;
  // Reset each field manually to ensure reactivity works correctly
  form.firstName = "";
  form.lastName = "";
  form.email = "";
  form.password = "";
  form.confirmPassword = "";
};
</script>




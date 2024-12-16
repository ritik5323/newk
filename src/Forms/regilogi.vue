<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <!-- Container -->
    <div class="container mx-auto">
      <div class="flex justify-center items-center px-6">
        <!-- Row -->
        <div class="w-full xl:w-3/4 lg:w-11/12 flex">
          <!-- Column -->
          <div class="mx-auto lg:w-7/12 border shadow-lg bg-white p-5 rounded-lg lg:rounded-l-none ">
            <h3 class="pt-4 text-2xl text-center">
              {{ isLogin ? "Login to Your Account" : "Create an Account" }}
            </h3>
            <form
              class="px-8 pt-6 pb-8 mb-4 bg-white rounded"
              @submit.prevent="handleSubmit"
            >
              <!-- Form Fields -->
              <div v-if="!isLogin">
                <!-- Name Fields (Only for Registration) -->
                <div class="mb-4 md:flex md:justify-between">
                  <div class="mb-4 md:mr-2 md:mb-0">
                    <label
                      class="block mb-2 text-sm font-bold text-gray-700"
                      for="firstName"
                    >
                      First Name
                    </label>
                    <input
                      v-model="form.firstName"
                      class="w-full px-3 py-2 text-sm leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline"
                      id="firstName"
                      type="text"
                      placeholder="First Name"
                    />
                  </div>
                  <div class="md:ml-2">
                    <label
                      class="block mb-2 text-sm font-bold text-gray-700"
                      for="lastName"
                    >
                      Last Name
                    </label>
                    <input
                      v-model="form.lastName"
                      class="w-full px-3 py-2 text-sm leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline"
                      id="lastName"
                      type="text"
                      placeholder="Last Name"
                    />
                  </div>
                </div>
              </div>
              <!-- Email Field -->
              <div class="mb-4">
                <label
                  class="block mb-2 text-sm font-bold text-gray-700"
                  for="email"
                >
                  Email
                </label>
                <input
                  v-model="form.email"
                  class="w-full px-3 py-2 mb-3 text-sm leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline"
                  id="email"
                  type="email"
                  placeholder="Email"
                />
              </div>
              <!-- Password Fields -->
              <div class="mb-4">
                <label
                  class="block mb-2 text-sm font-bold text-gray-700"
                  for="password"
                >
                  Password
                </label>
                <input
                  v-model="form.password"
                  class="w-full px-3 py-2 mb-3 text-sm leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline"
                  id="password"
                  type="password"
                  placeholder="******************"
                />
              </div>
              <div v-if="!isLogin" class="mb-4">
                <label
                  class="block mb-2 text-sm font-bold text-gray-700"
                  for="confirmPassword"
                >
                  Confirm Password
                </label>
                <input
                  v-model="form.confirmPassword"
                  class="w-full px-3 py-2 mb-3 text-sm leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline"
                  id="confirmPassword"
                  type="password"
                  placeholder="******************"
                />
              </div>
              <!-- Submit Button -->
              <div class="mb-6 text-center">
                <button
                  class="w-full px-4 py-2 font-bold text-white bg-blue-500 rounded-full hover:bg-blue-700 focus:outline-none focus:shadow-outline"
                  type="submit"
                >
                  {{ isLogin ? "Login" : "Register Account" }}
                </button>
              </div>
              <hr class="mb-6 border-t" />
              <!-- Toggle Form -->
              <div class="text-center">
                <a
                  class="inline-block text-sm text-blue-500 align-baseline hover:text-blue-800 cursor-pointer"
                  @click="toggleForm"
                >
                  {{ isLogin
                    ? "Don't have an account? Register!"
                    : "Already have an account? Login!" }}
                </a>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
</template>

<script setup lang="ts">
import { reactive, ref } from "vue";

// Form state
const form = reactive({
  firstName: "",
  lastName: "",
  email: "",
  password: "",
  confirmPassword: "",
});

// State to toggle between login and registration forms
const isLogin = ref(true);

// Handle form submission
const handleSubmit = () => {
  if (isLogin.value) {
    // Login logic
    if (!form.email || !form.password) {
      alert("Please enter both email and password.");
      return;
    }
    alert("Logged in successfully!");
  } else {
    // Registration logic
    if (
      !form.firstName ||
      !form.lastName ||
      !form.email ||
      !form.password ||
      !form.confirmPassword
    ) {
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

// Toggle between login and registration forms
const toggleForm = () => {
  isLogin.value = !isLogin.value;
  // Reset form fields
  form.firstName = "";
  form.lastName = "";
  form.email = "";
  form.password = "";
  form.confirmPassword = "";
};
</script>

<style scoped>
/* Additional custom styles if needed */
</style>

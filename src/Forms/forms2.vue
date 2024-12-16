<template>
  <div class="p-6 max-w-xl mx-auto bg-white shadow-md rounded-md">
    <!-- Form Section (Only visible when not saved) -->
    <form v-if="!isSaved" @submit.prevent="handleSave">
      <!-- Username -->
      <div class="mb-4">
        <label for="username" class="block text-sm font-medium text-gray-700">Username</label>
        <input
          type="text"
          id="username"
          v-model="form.username"
          placeholder="Enter username"
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        />
      </div>

      <!-- Email -->
      <div class="mb-4">
        <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
        <input
          type="email"
          id="email"
          v-model="form.email"
          placeholder="Enter email"
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        />
      </div>

      <!-- About -->
      <div class="mb-4">
        <label for="about" class="block text-sm font-medium text-gray-700">About</label>
        <textarea
          id="about"
          v-model="form.about"
          placeholder="Write about yourself"
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        ></textarea>
      </div>

      <!-- Save Button -->
      <div class="flex justify-end">
        <button
          type="submit"
          class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-500"
        >
          Save
        </button>
      </div>
    </form>

    <!-- Display Saved Data (Only visible after saving) -->
    <div v-else class="mt-6 p-4 bg-gray-100 rounded-md">
      <h3 class="text-lg font-semibold mb-2">Saved Details:</h3>
      <p><strong>Username:</strong> {{ savedData.username }}</p>
      <p><strong>Email:</strong> {{ savedData.email }}</p>
      <p><strong>About:</strong> {{ savedData.about }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

// Reactive form data
const form = ref({
  username: '',
  email: '',
  about: '',
});

// Reactive state for saved data
const savedData = ref({});
const isSaved = ref(false);

// Handle Save
const handleSave = () => {
  if (form.value.username && form.value.email && form.value.about) {
    savedData.value = { ...form.value }; // Copy form data to savedData
    isSaved.value = true; // Hide form and show saved details
  } else {
    alert('Please fill in all fields before saving.');
  }
};
</script>

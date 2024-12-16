<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="flex items-center justify-center min-h-screen bg-gradient-to-r from-blue-200 via-indigo-300 to-purple-200">
    <div
      class="w-full max-w-lg bg-white shadow-lg rounded-lg p-6 sm:p-8"
    >
      <h2
        class="text-2xl font-bold text-center text-indigo-700 mb-6"
      >
        {{ isSaved ? "Your Profile" : "Edit Your Profile" }}
      </h2>

      <!-- Form View -->
      <form v-if="!isSaved" class="space-y-6">
        <!-- Username -->
        <div>
          <label for="username" class="block text-sm font-medium text-gray-700">Username</label>
          <input
            type="text"
            id="username"
            v-model="form.username"
            placeholder="Enter username"
            class="mt-1 block w-full rounded-md border border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm text-gray-700 placeholder-gray-400"
          />
        </div>

        <!-- Name -->
        <div>
          <label for="name1" class="block text-sm font-medium text-gray-700">Name</label>
          <input
            type="text"
            id="name1"
            v-model="form.name1"
            placeholder="Enter name"
            class="mt-1 block w-full rounded-md border border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm text-gray-700 placeholder-gray-400"
          />
        </div>

        <!-- Email -->
        <div>
          <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
          <input
            type="email"
            id="email"
            v-model="form.email"
            placeholder="Enter email"
            class="mt-1 block w-full rounded-md border border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm text-gray-700 placeholder-gray-400"
          />
        </div>

        <!-- About -->
        <div>
          <label for="about" class="block text-sm font-medium text-gray-700">About</label>
          <textarea
            id="about"
            v-model="form.about"
            placeholder="Write about yourself"
            rows="4"
            class="mt-1 block w-full rounded-md border border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm text-gray-700 placeholder-gray-400"
          ></textarea>
        </div>
      </form>

      <!-- Profile View -->
      <div v-if="isSaved" class="space-y-6">
        <!-- Username -->
        <div>
          <label class="block text-sm font-medium text-gray-700">Username</label>
          <div class="mt-1 text-gray-900 text-sm font-medium">{{ form.username }}</div>
        </div>
        <!-- Name -->
        <div>
          <label class="block text-sm font-medium text-gray-700">Name</label>
          <div class="mt-1 text-gray-900 text-sm font-medium">{{ form.name1 }}</div>
        </div>

        <!-- Email -->
        <div>
          <label class="block text-sm font-medium text-gray-700">Email</label>
          <div class="mt-1 text-gray-900 text-sm font-medium">{{ form.email }}</div>
        </div>

        <!-- About -->
        <div>
          <label class="block text-sm font-medium text-gray-700">About</label>
          <div class="mt-1 text-gray-900 text-sm font-medium">{{ form.about }}</div>
        </div>
      </div>

      <!-- Buttons -->
      <div class="flex justify-end mt-6 gap-4">
        <button
          v-if="isSaved"
          @click.prevent="enableEdit"
          class="px-6 py-2 bg-blue-600 text-white rounded-md hover:bg-blue-500 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-offset-2"
        >
          Edit
        </button>
        <button
          v-else
          @click.prevent="handleSave"
          class="px-6 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-400 focus:ring-offset-2"
        >
          Save
        </button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

// Form state
const form = ref({
  username: '',
  name1: '',
  email: '',
  about: '',
});

const isSaved = ref(false);

// Handle Save
const handleSave = () => {
  if (form.value.username && form.value.name1 && form.value.email && form.value.about) {
    isSaved.value = true; // Replace inputs with non-editable fields
  } else {
    alert('Please fill in all fields before saving.');
  }
};

// Enable Editing
const enableEdit = () => {
  isSaved.value = false; // Switch back to input fields
};
</script>







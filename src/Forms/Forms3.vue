<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="max-w-xl mx-auto bg-white shadow-md rounded-md p-6">
    <!-- Username -->
    <div class="mb-4">
      <label for="username" class="block text-sm font-medium text-gray-700">Username</label>
      <div
        v-if="isSaved"
        class="mt-1 block w-full  border-gray-300 py-2 text-sm text-gray-900"
      >
        {{ form.username }}
      </div>
      <input
        v-else
        type="text"
        id="username"
        v-model="form.username"
        placeholder="Enter username"
        class="mt-1 block w-full rounded-md  border-gray-300 shadow-sm border focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
      />
    </div>

      <!-- name -->
      <div class="mb-4">
      <label for="name1" class="block text-sm font-medium text-gray-700">Name</label>
      <div
        v-if="isSaved"
        class="mt-1 block w-full  border-gray-300 py-2 text-sm text-gray-900"
      >
        {{ form.name1 }}
      </div>
      <input
        v-else
        type="text"
        id="name1"
        v-model="form.name1"
        placeholder="Enter name"
        class="mt-1 block w-full rounded-md border-gray-300 shadow-sm border focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
      />
    </div>

    <!-- Email -->
    <div class="mb-4">
      <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
      <div
        v-if="isSaved"
        class="mt-1 block w-full  border-gray-300 py-2 text-sm text-gray-900"
      >
        {{ form.email }}
      </div>
      <input
        v-else
        type="email"
        id="email"
        v-model="form.email"
        placeholder="Enter email"
        class="mt-1 block w-full rounded-md border-gray-300 shadow-sm border focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
      />
    </div>

    <!-- About -->
    <div class="mb-4">
      <label for="about" class="block text-sm font-medium text-gray-700">About</label>
      <div
        v-if="isSaved"
        class="mt-1 block w-full  border-gray-300 py-2 text-sm  text-gray-900"
      >
        {{ form.about }}
      </div>
      <textarea
        v-else
        id="about"
        v-model="form.about"
        placeholder="Write about yourself"
        class="mt-1 block w-full rounded-md border-gray-300 shadow-sm border focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
      ></textarea>
    </div>

    <!-- Buttons -->
    <div class="flex justify-end mt-4 gap-4">
      <button
        v-if="isSaved"
        @click="enableEdit"
        class="px-4 py-2 bg-blue-600 text-white rounded-md hover:bg-blue-500"
      >
        Edit
      </button>
      <button
        v-else
        @click="handleSave"
        class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-500"
      >
        Save
      </button>
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

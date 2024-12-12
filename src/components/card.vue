<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class=" bg-white rounded-lg shadow-md overflow-hidden">
    <img class="w-full h-48 object-cover" :src="imageSrc" :alt="imageAlt" />
    <div class="p-4">
      <h3 class="text-xl font-bold">{{ cardTitle }}</h3>
      <p class="text-gray-600 mt-2">{{ cardDescription }}</p>
      <button
        class="bg-blue-500 text-white px-4 py-2 mt-4 rounded hover:bg-blue-600"
        @click="handleClick"
      >
        {{ buttonText }}
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

// Define props
defineProps({
  imageSrc: {
    type: String,
    default: "https://via.placeholder.com/400",
  },
  imageAlt: {
    type: String,
    default: "Card Image",
  },
  cardTitle: {
    type: String,
    default: "Card Title",
  },
  cardDescription: {
    type: String,
    default: "This is a description of the card content.",
  },
  buttonText: {
    type: String,
    default: "Learn More",
  },
});

// Define methods or logic
const handleClick = () => {
  alert("Button clicked!");
};
</script>

<style scoped>
/* Add scoped styles here if necessary */
</style>

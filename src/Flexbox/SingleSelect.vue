<script setup lang="ts">
import { ref } from 'vue'

const selected = ref('')
</script>

<template>
  <!-- <span> Selected: {{ selected }}</span> -->
  <div> Selected: {{ selected }}</div>

  <select v-model="selected">
    <option disabled value="">Please select one</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
</template>
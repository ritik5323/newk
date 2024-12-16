<script setup lang="ts">
import { ref,  } from 'vue';

// const selected = ref('');
</script>

<template>
<div> selected: {{ selected }}</div>
<select v-modal="selected">
<option value="" disabled>Please select one</option>
<option>A</option>
<option>b</option>
<option>c</option>
</select>

<!-- <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-6 gap-4 p-4">
  <div class="bg-blue-200 p-2">Item 1</div>
  <div class="bg-blue-300 p-2">Item 2</div>
  <div class="bg-blue-400 p-2">Item 3</div>
  <div class="bg-blue-500 p-2">Item 4</div>
  <div class="bg-blue-600 p-2">Item 5</div>
  <div class="bg-blue-700 p-2">Item 6</div>
</div> -->

<!-- <div class="grid grid-cols-[200px_minmax(900px,_1fr)_100px] gap-4 p-4 border">
  <div class="bg-blue-200 p-2">Column 1</div>
  <div class="bg-blue-300 p-2">Column 2</div>
  <div class="bg-blue-400 p-2">Column 3</div>
</div> -->

<!-- <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
  <div class="bg-blue-200 p-4">Item 1</div>
  <div class="bg-blue-300 p-4">Item 2</div>
  <div class="bg-blue-400 p-4">Item 3</div>
  <div class="bg-blue-500 p-4">Item 4</div>
  <div class="bg-blue-600 p-4">Item 5</div>
  <div class="bg-blue-700 p-4">Item 6</div>
</div> -->










</template>
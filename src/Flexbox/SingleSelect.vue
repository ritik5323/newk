<script setup lang="ts">
import { ref,  } from 'vue';

// const selected = ref('');
</script>

<template>
<!-- <div> selected: {{ selected }}</div>
<select v-modal="selected">
<option>Please select one</option>
<option>A</option>
<option>b</option>
<option>c</option>
</select> -->

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


<div class="grid grid-cols-1 md:grid-cols-3 gap-4 p-4 border border-gray-300">
    <!-- Header Section with Flexbox for Navigation -->
    <header class="col-span-1 md:col-span-3 flex justify-between items-center bg-blue-200 p-4">
      <div class="text-xl font-semibold">My Website</div>
      <nav class="flex space-x-4">
        <a href="#" class="hover:text-blue-500">Home</a>
        <a href="#" class="hover:text-blue-500">About</a>
        <a href="#" class="hover:text-blue-500">Contact</a>
      </nav>
    </header>

    <!-- Sidebar Section -->
    <aside class="bg-gray-200 p-4">
      <h3 class="font-semibold">Sidebar</h3>
      <ul>
        <li><a href="#" class="hover:text-blue-500">Link 1</a></li>
        <li><a href="#" class="hover:text-blue-500">Link 2</a></li>
        <li><a href="#" class="hover:text-blue-500">Link 3</a></li>
      </ul>
    </aside>

    <!-- Main Content Section with Flexbox for Content Alignment -->
    <main class="bg-white p-4 col-span-1 md:col-span-2">
      <div class="flex flex-col items-start space-y-4">
        <div class="bg-green-200 p-4">Welcome to my website!</div>
        <div class="bg-yellow-200 p-4">Here is some more content...</div>
        <div class="bg-red-200 p-4">Final content block</div>
      </div>
    </main>

    <!-- Footer Section -->
    <footer class="col-span-1 md:col-span-3 bg-blue-300 p-4 text-center">
      &copy; 2024 My Website
    </footer>
  </div>







</template>
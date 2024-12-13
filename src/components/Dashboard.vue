<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="bg-gray-900 text-white min-h-screen p-8">
    <!-- Header -->
    <div class="mb-8">
      <h1 class="text-blue-400 text-sm font-bold uppercase">Deploy faster</h1>
      <h2 class="text-3xl font-semibold">Everything you need to deploy your app</h2>
    </div>

    <!-- Main Content -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
      <!-- Releases Section -->
      <div class="bg-gray-800 p-6 rounded-lg shadow-md">
        <h3 class="text-lg font-bold mb-4">Releases</h3>
        <ul class="space-y-4">
          <li class="flex justify-between items-center">
            <div>
              <p class="text-blue-400 font-semibold">Pictionary - mobile-app</p>
              <p class="text-sm text-gray-400">Deployed 14 days ago</p>
            </div>
            <button class="bg-blue-500 text-sm px-4 py-2 rounded">Retry</button>
          </li>
          <li class="flex justify-between items-center">
            <div>
              <p class="text-blue-400 font-semibold">Brainstorm Labs - admin-tool</p>
              <p class="text-sm text-gray-400">Deployed 21 days ago</p>
            </div>
            <button class="bg-blue-500 text-sm px-4 py-2 rounded">Retry</button>
          </li>
          <li class="flex justify-between items-center">
            <div>
              <p class="text-blue-400 font-semibold">Teamwork Lab - admin-tool</p>
              <p class="text-sm text-gray-400">Deployed 26 days ago</p>
            </div>
            <button class="bg-blue-500 text-sm px-4 py-2 rounded">Retry</button>
          </li>
        </ul>
      </div>

      <!-- Integrations Section -->
      <div class="bg-gray-800 p-6 rounded-lg shadow-md">
        <h3 class="text-lg font-bold mb-4">Integrations</h3>
        <ul class="space-y-4">
          <li class="flex items-center justify-between">
            <span>Google Console</span>
            <button class="bg-blue-500 text-sm px-4 py-2 rounded">Connect</button>
          </li>
          <li class="flex items-center justify-between">
            <span>Discord</span>
            <button class="bg-blue-500 text-sm px-4 py-2 rounded">Connect</button>
          </li>
          <li class="flex items-center justify-between">
            <span>Adobe Creative Cloud</span>
            <button class="bg-blue-500 text-sm px-4 py-2 rounded">Connect</button>
          </li>
        </ul>
      </div>

      <!-- Advanced Access Control -->
      <div class="bg-gray-800 p-6 rounded-lg shadow-md">
        <h3 class="text-lg font-bold mb-4">Security</h3>
        <p class="text-gray-400 text-sm">Advanced access control features ensure security across your deployment pipelines.</p>
        <div class="flex items-center space-x-4 mt-4">
          <img class="w-10 h-10 rounded-full" src="https://via.placeholder.com/40" alt="User 1" />
          <img class="w-10 h-10 rounded-full" src="https://via.placeholder.com/40" alt="User 2" />
        </div>
      </div>

      <!-- Performance Section -->
      <div class="bg-gray-800 p-6 rounded-lg shadow-md">
        <h3 class="text-lg font-bold mb-4">Performance</h3>
        <p class="text-gray-400 text-sm">Lightning-fast builds ensure minimal downtime and optimal user experience.</p>
        <div class="mt-4 grid grid-cols-3 gap-4 text-center">
          <div>
            <p class="text-2xl font-bold">405</p>
            <p class="text-sm text-gray-400">Deployments</p>
          </div>
          <div>
            <p class="text-2xl font-bold">3.65</p>
            <p class="text-sm text-gray-400">Avg deploy time</p>
          </div>
          <div>
            <p class="text-2xl font-bold">3</p>
            <p class="text-sm text-gray-400">Teams</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
</style>

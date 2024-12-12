<script setup lang="ts">
import { ref,  } from 'vue';

const componen = ref('');
</script>

<template>
<div> selected: {{ componen }}</div>
<select v-modal="componen">
<option>Please select one</option>
<option>A</option>
<option>b</option>
<option>c</option>
</select>


</template>
<script setup lang="ts">
import { ref,  } from 'vue';

const selected = ref('');
</script>

<template>
<div> selected: {{ selected }}</div>
<select v-modal="selected">
<option>Please select one</option>
<option>A</option>
<option>b</option>
<option>c</option>
</select>


</template>
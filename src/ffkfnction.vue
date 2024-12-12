

// import { ref, onMounted } from 'vue';

// const count = ref(0)

// // Functions that mutate state and trigger updates
// function increment() {
//   count.value++
// }

// // Lifecycle hooks
// onMounted(() => {
//   console.log(`The initial count is ${count.value}.`)
// })
// 

<!-- // <template>
//   <button @click="increment" class="font-bold text-red-400">
//     Count is: {{ count }}
//   </button>
// </template> -->
<!-- <script setup lang="ts">
import { computed, reactive } from 'vue';

const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
})

// a computed ref
const publishedBooksMessage = computed(() => {
  return author.books.length > 0 ? 'Yes' : 'No'
})
</script>

<template>
  <p>Has published books:</p>
  <span>{{ publishedBooksMessage }}</span>
</template> -->

<!-- <template>
  <div>
    <p>Full Name: {{ fullName }}</p>
    <input v-model="fullName" placeholder="Enter full name" />
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const firstName = ref('John')
const lastName = ref('Doe')

const fullName = computed({
  get() {
    return firstName.value + ' ' + lastName.value
  },
  set(newValue) {
    [firstName.value, lastName.value] = newValue.split(' ')
  }
})
</script> -->



// import { reactive } from 'vue';

// const myObject = reactive({
//   title: 'How to do lists in Vue',
//   author: 'Jane Doe',
//   publishedAt: '2016-04-10',
// });
// 

<!-- // <template>
//   <ul>
//     <li v-for="(value, key,index) in myObject" :key="key">
//      {{ index }}.  {{ key }}: {{ value }}
//     </li>
//   </ul>
// </template> -->

<script setup lang="ts">
import { ref } from 'vue'

const name = ref('Vue.js')

function greet(event) {
  alert(`Hello ${name.value}!`)
  // `event` is the native DOM event
  if (event) {
    alert(event.target.tagName)
  }
}
</script>

<template>
	<button @click="greet">Greet</button>
</template>
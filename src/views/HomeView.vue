<script setup lang="ts">
import { computed, reactive, ref } from 'vue'
import MyChild from '../components/MyChild.vue'
const count = ref(0)
const state = reactive({
  count: 0
})
const author = reactive({
  name: 'John Doe',
  books: ['Vue 2 - Advanced Guide', 'Vue 3 - Basic Guide', 'Vue 4 - The Mystery']
})
const publishedBooksMessage = computed(() => {
  return author.books.length > 0 ? 'yes' : 'no'
})
const increment = () => {
  count.value++
  author.books.push('New Book')
}
const stateIncrement = () => {
  state.count++
  author.books = []
}
const msg = ref('hhh')
</script>

<template>
  <main>
    count ----- {{ count }} state.count ----- {{ state.count }}
    <button @click="increment">count</button>
    <button @click="stateIncrement">state</button>
    <p>Has published books:</p>
    <span>{{ publishedBooksMessage }}</span>
    <button @click="stateIncrement">state</button>
    --------------
    {{ msg }}
    <MyChild v-model:inputVal="msg" :count="12" title="Mychild" msg="444" />
  </main>
</template>

<script lang="ts" setup>
const props = defineProps<{
  title?: String
  msg?: String
  count: Number
}>()
const inputVal = defineModel('inputVal')
</script>

<template>
  <div>
    Child
    {{ props.title }}
    {{ props.count }}
    <div><input v-model="inputVal" /></div>
  </div>
</template>

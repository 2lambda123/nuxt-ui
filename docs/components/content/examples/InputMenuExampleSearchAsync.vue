<script setup>
const loading = ref(false)
const selected = ref()

async function search (q) {
  loading.value = true

  const users = await $fetch('https://jsonplaceholder.typicode.com/users', { params: { q } })

  loading.value = false

  return users
}
</script>

<template>
  <UInputMenu
    v-model="selected"
    :search="search"
    :loading="loading"
    placeholder="Search for a user..."
    option-attribute="name"
    trailing
    by="id"
  />
</template>

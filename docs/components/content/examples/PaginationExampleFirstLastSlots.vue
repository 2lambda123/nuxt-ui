<script setup>
const page = ref(1)
const items = ref(Array(55))
</script>

<template>
  <UPagination v-model="page" :total="items.length" :ui="{ rounded: 'first-of-type:rounded-s-md last-of-type:rounded-e-md' }">
    <template #first="{ onClick }">
      <UTooltip text="First page">
        <UButton icon="i-heroicons-arrow-uturn-left" color="primary" :ui="{ rounded: 'rounded-full' }" class="rtl:[&_span:first-child]:rotate-180 me-2" @click="onClick" />
      </UTooltip>
    </template>

    <template #last="{ onClick }">
      <UTooltip text="Last page">
        <UButton icon="i-heroicons-arrow-uturn-right-20-solid" color="primary" :ui="{ rounded: 'rounded-full' }" class="rtl:[&_span:last-child]:rotate-180 ms-2" @click="onClick" />
      </UTooltip>
    </template>
  </UPagination>
</template>

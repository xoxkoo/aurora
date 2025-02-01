<template>
  <div class="p-6 rounded-2xl bg-white/5 backdrop-blur-lg">
    <h3 class="text-xl font-medium mb-3">{{ title }}</h3>
    <p class="text-gray-400 leading-relaxed">{{ description }}</p>
  </div>
</template>

<script setup lang="ts">
defineProps({
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  }
})
</script>
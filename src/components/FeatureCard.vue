<template>
	<div class="rounded-2xl bg-white/5 p-6 backdrop-blur-lg">
		<h3 class="mb-3 text-xl font-medium">{{ title }}</h3>
		<p class="leading-relaxed text-gray-400">{{ description }}</p>
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

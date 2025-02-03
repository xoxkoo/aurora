<template>
	<div class="fixed bottom-0 left-1/2 -translate-x-1/2 transform">
		<button
			class="group flex h-10 items-center space-x-2 rounded-t-full border border-gray-600 bg-white px-6 text-black transition-all duration-300 hover:bg-white/90 hover:px-8"
			@click="$emit('downloadApp')"
		>
			<div
				class="absolute inset-0 rounded-t-full bg-gradient-to-r from-gray-100 to-gray-200 opacity-0 transition-opacity group-hover:opacity-20"
			/>
			<IconDownload class="h-5 w-5 text-black" />
			<span class="hidden text-sm font-medium group-hover:inline">Download</span>
		</button>
	</div>
</template>
<script setup lang="ts">
import { defineEmits } from 'vue'
import IconDownload from './icons/IconDownload.vue'

defineEmits(['downloadApp'])
</script>

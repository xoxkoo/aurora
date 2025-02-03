<template>
	<button class="button rounded-xl px-6 py-3" @click="$emit('downloadApp')">
		<span class="flex items-center space-x-2">
			<IconDownload class="h-5 w-5" />
			<span>Download for macOS</span>
		</span>
	</button>
</template>

<script setup lang="ts">
import { defineEmits } from 'vue'
import IconDownload from './icons/IconDownload.vue'

defineEmits(['downloadApp'])
</script>

<style>
.button {
	width: fit-content;
	display: flex;
	gap: 0.4rem;
	border: none;
	cursor: pointer;
	/* background: linear-gradient(15deg, #702ae9, #6a3ecf, #552fd3, #2821ec, #552fd3, #6a3ecf, #702ae9) */
	background: linear-gradient(15deg, #c084fc, #a084fc, #60a5fa, #a084fc, #c084fc) no-repeat;
	background-size: 300%;
	background-position: left center;
	transition: background 0.3s ease;
	color: #fff;
}

.button:hover {
	background-size: 320%;
	background-position: right center;
}
</style>

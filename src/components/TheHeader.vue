<template>
	<header
		:class="[
			'fixed z-50 w-full py-4 transition-all duration-300',
			{ 'bg-black/80 py-1 shadow-2xl backdrop-blur-lg': scrolled }
		]"
	>
		<div class="container mx-auto px-6">
			<div class="flex items-center justify-between">
				<div class="flex items-center space-x-3">
					<img
						src="../assets/images/logo.png"
						alt="Logo"
						class="h-10 w-10 rounded-lg border shadow-lg transition-transform hover:scale-105"
						width="40"
						height="40"
					/>
					<span class="text-lg font-medium tracking-wider text-transparent text-white">AURORA</span>
				</div>
				<nav class="hidden items-center space-x-8 md:flex">
					<a href="#features" class="text-gray-300 transition-colors hover:text-white">Features</a>
					<a href="#" class="text-gray-300 transition-colors hover:text-white">Demo</a>
					<a
						href="https://github.com/xoxkoo/aurora/releases/latest"
						target="_blank"
						class="rounded-lg bg-white/10 px-4 py-2 transition-colors hover:bg-white/20"
					>
						Download
					</a>
				</nav>
			</div>
		</div>
	</header>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, defineEmits } from 'vue'
defineEmits(['downloadApp'])

const scrolled = ref(false)

const handleScroll = () => {
	scrolled.value = window.scrollY > 20
}

onMounted(() => {
	window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
	window.removeEventListener('scroll', handleScroll)
})
</script>

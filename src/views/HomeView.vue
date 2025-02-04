<template>
	<div class="relative min-h-screen bg-black text-white">
		<Aurora />
		<TheHeader />

		<main class="relative">
			<div class="container mx-auto px-6 pb-20 pt-32">
				<div class="mx-auto max-w-4xl text-center">
					<TheHero />
					<div class="flex flex-col justify-center space-y-4 sm:flex-row sm:space-x-6 sm:space-y-0">
						<DownloadButton @downloadApp="downloadApp" />
						<DemoButton />
					</div>
				</div>
			</div>

			<AppPreview />

			<div id="features" class="container mx-auto px-6 py-20">
				<h2 class="mb-16 text-center text-3xl font-bold">
					<span class="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">
						Features
					</span>
				</h2>
				<div class="grid gap-8 md:grid-cols-3">
					<FeatureCard
						v-for="feature in features"
						:key="feature.title"
						:title="feature.title"
						:description="feature.description"
					/>
				</div>
			</div>

			<BuyMeCoffee />
		</main>

		<TheFooter />

		<FixedButton @downloadApp="downloadApp" />
	</div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import Aurora from '@/components/AuroraBorealis.vue'
import FeatureCard from '@/components/FeatureCard.vue'
import TheHeader from '@/components/TheHeader.vue'
import TheFooter from '@/components/TheFooter.vue'
import BuyMeCoffee from '@/components/BuyMeCoffee.vue'
import FixedButton from '@/components/FixedButton.vue'
import DownloadButton from '@/components/DownloadButton.vue'
import DemoButton from '@/components/DemoButton.vue'
import AppPreview from '@/components/AppPreview.vue'
import TheHero from '@/components/TheHero.vue'

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

const features = [
	{
		title: 'Menu Bar Quick Access',
		description:
			'Start your timer and track habits directly from the menu bar without opening the main app.'
	},
	{
		title: 'Focus Timer',
		description:
			'Built-in timer with customizable durations to help you stay focused on your habits.'
	},
	{
		title: 'Beautiful Design',
		description:
			'Clean, minimal interface with aurora-inspired visuals for a delightful user experience.'
	}
]

const downloadApp = () => {
	window.open('https://github.com/xoxkoo/aurora/releases/download/v0.0.2/Aurora.dmg', '_blank')
}
</script>

<style>
@keyframes float-slow {
	0%,
	100% {
		transform: translate(0, 0);
	}
	50% {
		transform: translate(20px, -20px);
	}
}

@keyframes float-slower {
	0%,
	100% {
		transform: translate(0, 0);
	}
	50% {
		transform: translate(-20px, -10px);
	}
}

.animate-float-slow {
	animation: float-slow 8s ease-in-out infinite;
}

.animate-float-slower {
	animation: float-slower 12s ease-in-out infinite;
}
</style>

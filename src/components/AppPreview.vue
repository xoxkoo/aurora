<!-- App Preview Section -->
<template>
	<div class="container mx-auto px-6 py-20">
		<img
			src="../assets/images/AppPreview.gif"
			alt="Loading"
			class="mx-auto mb-20 rounded-3xl"
			width="500"
		/>

		<div class="relative mx-auto max-w-5xl">
			<div
				class="absolute inset-0 bg-gradient-to-r from-blue-500/30 to-purple-500/30 blur-3xl"
			></div>

			<div class="relative rounded-3xl border border-white/10 bg-white/5 p-8 backdrop-blur-xl">
				<div class="grid items-center gap-8 md:grid-cols-2">
					<div class="space-y-6">
						<h2 class="text-3xl font-bold text-white">Minimal Design, Maximum Focus.</h2>
						<p class="text-gray-400">
							Experience a minimal interface with aurora-inspired visuals for a delightful user
							experience.
						</p>
					</div>

					<img
						src="../assets/images/app-preview.png"
						alt="App Preview"
						class="h-full w-full rounded-xl object-cover"
					/>
				</div>
			</div>

			<!-- Menu Bar Preview - Floating effect -->
			<div
				class="absolute -top-8 right-8 w-72 animate-float-slow overflow-hidden rounded-xl shadow-2xl backdrop-blur-xl"
			>
				<img src="../assets/images/menu-preview.png" alt="Menu Bar Preview" class="w-full" />
			</div>
		</div>
	</div>
</template>

<style scoped>
/* Existing animations */
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

/* Additional hover effect */
.rounded-3xl {
	transition: transform 0.3s ease-in-out;
}

.rounded-3xl:hover {
	transform: translateY(-4px);
}
</style>

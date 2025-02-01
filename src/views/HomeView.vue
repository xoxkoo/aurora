<template>
  <div class="min-h-screen bg-black text-white relative">
    <Aurora />

    <!-- Header -->
    <header :class="[
      'fixed w-full z-50 transition-all duration-300',
      { 'bg-black/80 backdrop-blur-lg': scrolled }
    ]">
      <div class="container mx-auto px-6 py-4">
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-3">
            <img src="../assets/images/logo.png" alt="Logo" class="w-10 h-10 rounded-lg"  width="40" height="40"/>
            <span class="text-lg font-medium tracking-wide">AURORA</span>
          </div>
        </div>
      </div>
    </header>

    <!-- Hero -->
    <main class="relative">
      <div class="container mx-auto px-6 pt-32 pb-20">
        <div class="max-w-4xl mx-auto text-center">
          <h1 class="text-6xl font-bold mb-8 bg-gradient-to-r from-blue-400 via-purple-400 to-blue-400 bg-clip-text text-transparent">
            Build Better Habits
          </h1>
          <p class="text-xl text-gray-300 mb-12 leading-relaxed">
            Minimal, beautiful habit tracking for macOS with focus timer and
            quick menu bar access.
          </p>
          <div class="flex justify-center space-x-6">
            <button class="group relative px-8 py-4 bg-white/10 hover:bg-white/20 backdrop-blur-lg rounded-2xl transition-all duration-300">
              <div class="absolute inset-0 rounded-2xl bg-gradient-to-r from-blue-500 to-purple-500 opacity-0 group-hover:opacity-20 transition-opacity" />
              <span class="flex items-center space-x-2">
                <IconDownload class="w-5 h-5" />
                <span>Download for macOS</span>
              </span>
            </button>
          </div>
        </div>
      </div>

      <!-- App Preview -->
      <div class="container mx-auto px-6 py-20">
        <div class="relative mx-auto max-w-5xl">
          <div class="aspect-[16/10] rounded-2xl overflow-hidden bg-gradient-to-br from-gray-900 to-gray-800 shadow-2xl">
            <img src="../assets/images/app-preview.png" alt="App Preview" class="w-full h-full object-cover" />
          </div>

          <!-- Menu Bar Preview -->
          <div class="absolute -top-8 right-8 w-72 bg-gray-900/95 backdrop-blur-xl rounded-xl overflow-hidden shadow-2xl border border-white/10">
            <div class="p-4">
              <div class="flex items-center justify-between mb-4">
                <div class="flex items-center space-x-2">
                  <div class="w-8 h-8 rounded-lg bg-blue-500" />
                  <span class="text-sm font-medium">Timer</span>
                </div>
              </div>
              <div class="text-center py-4">
                <span class="text-4xl font-light">25:00</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Features -->
      <div class="container mx-auto px-6 py-20">
        <div class="grid md:grid-cols-3 gap-8">
          <FeatureCard
            v-for="feature in features"
            :key="feature.title"
            :title="feature.title"
            :description="feature.description"
          />
        </div>
      </div>
    </main>

    <!-- Footer -->
    <footer class="relative border-t border-white/10">
      <div class="container mx-auto px-6 py-8">
        <div class="text-center text-sm text-gray-500">
          © 2025 AuroraHabit. All rights reserved.
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import IconDownload from '@/components/icons/IconDownload.vue'
import Aurora from '@/components/AuroraBorealis.vue'
import FeatureCard from '@/components/FeatureCard.vue'

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
    title: "Menu Bar Quick Access",
    description: "Start your timer and track habits directly from the menu bar without opening the main app."
  },
  {
    title: "Focus Timer",
    description: "Built-in timer with customizable durations to help you stay focused on your habits."
  },
  {
    title: "Beautiful Design",
    description: "Clean, minimal interface with aurora-inspired visuals for a delightful user experience."
  }
]
</script>

<style>
@keyframes float-slow {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(20px, -20px); }
}

@keyframes float-slower {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(-20px, -10px); }
}

.animate-float-slow {
  animation: float-slow 8s ease-in-out infinite;
}

.animate-float-slower {
  animation: float-slower 12s ease-in-out infinite;
}
</style>
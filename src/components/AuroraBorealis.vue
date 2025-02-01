<template>
  <div class="absolute inset-0 overflow-hidden">
    <svg class="w-full h-full opacity-30" viewBox="0 0 1000 1000" preserveAspectRatio="none">
      <defs>
        <radialGradient id="aurora1" cx="50%" cy="50%" r="50%">
          <stop offset="0%" stop-color="#4C6EF5" stop-opacity="0.3" />
          <stop offset="100%" stop-color="#4C6EF5" stop-opacity="0" />
        </radialGradient>
        <radialGradient id="aurora2" cx="50%" cy="50%" r="50%">
          <stop offset="0%" stop-color="#9333EA" stop-opacity="0.3" />
          <stop offset="100%" stop-color="#9333EA" stop-opacity="0" />
        </radialGradient>
      </defs>
      <g class="animate-float-slow">
        <path d="M0,1000 C300,800 400,600 1000,800 L1000,1000 L0,1000 Z" fill="url(#aurora1)" />
      </g>
      <g class="animate-float-slower">
        <path d="M0,1000 C500,900 800,700 1000,900 L1000,1000 L0,1000 Z" fill="url(#aurora2)" />
      </g>
    </svg>
  </div>
</template>
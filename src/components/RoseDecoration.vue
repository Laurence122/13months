<template>
  <div class="roses">
    <svg v-for="n in 3" :key="n" class="rose" viewBox="0 0 64 64" width="48" height="48">
      <circle cx="32" cy="32" r="18" fill="#e75480"/>
      <ellipse cx="32" cy="32" rx="12" ry="18" fill="#ffb6c1"/>
      <ellipse cx="32" cy="32" rx="8" ry="12" fill="#e75480"/>
      <ellipse cx="32" cy="32" rx="4" ry="6" fill="#fff0f5"/>
      <rect x="30" y="44" width="4" height="16" rx="2" fill="#4caf50"/>
    </svg>
  </div>
</template>

<script setup>
// No logic needed, just decoration
</script>

<style scoped>
.roses {
  display: flex;
  justify-content: center;
  gap: 24px;
  margin-bottom: 24px;
}
.rose {
  filter: drop-shadow(0 2px 8px #e7548055);
  animation: sway 3s ease-in-out infinite alternate;
}
.rose:nth-child(2) {
  animation-delay: 1s;
}
.rose:nth-child(3) {
  animation-delay: 2s;
}
@keyframes sway {
  0% { transform: rotate(-5deg) scale(1); }
  100% { transform: rotate(5deg) scale(1.05); }
}
</style>

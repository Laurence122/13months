

<script setup>
import HelloWorld from './components/HelloWorld.vue'
import LoginBook from './components/LoginBook.vue'
import RoseDecoration from './components/RoseDecoration.vue'
</script>

<template>
  <div class="app-bg">
    <RoseDecoration />
    <LoginBook>
      <HelloWorld />
    </LoginBook>
  </div>
</template>

<style scoped>
body, .app-bg {
  min-height: 100vh;
  min-width: 100vw;
  width: 100vw;
  height: 100vh;
  background: linear-gradient(135deg, #ffd6e0 0%, #ffe3f0 100%);
  margin: 0;
  padding: 0;
  overflow: hidden;
}
.app-bg {
  min-height: 100vh;
  min-width: 100vw;
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-sizing: border-box;
  padding: 0;
}
</style>

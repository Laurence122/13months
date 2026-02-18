
<script setup>
import { ref } from 'vue'

const pages = [
  {
    title: 'To my Love',
    content: [
      'happy 13th months with a full of love. Sa ngayon ito na lang muna wala akong maibigay na regalo. Sana ma appreciate mo ito kahit paano. Mahal na mahal kita. Sorry sa mga pagkukulang ko bilang isang bf. Palagi kong kakayanin na mapasaya at maibigay ang bawat naisin mo madama mo lng na mahal na mahal kita. ILOVEYOUSOMUCH BABY MWAAA',
      '',
      'sincerely yours',
      'your Future Engineer Laurence'
    ]
  },
  { title: 'January', content: ['unang calap natin na mag kasama'], image: '/photos/january2025.jpg' },
  { title: 'February', content: ['dagat with u love'], image: '/photos/february2025.jpg' },
  { title: 'March', content: ['dagat ft. takas'], image: '/photos/march.jpg' },
  { title: 'April', content: ['sinama sa pag bind hehe'], image: '/photos/april.jpg' },
  { title: 'May', content: [' no pic ldr, cutie mo here '], image: '/photos/may.jpg' },
  { title: 'June', content: ['umuwi kana here tas wala pa din us pic'], image: '/photos/june.jpg' },
  { title: 'July', content: ['nag open ng acc sa bdo'], image: '/photos/july.jpg' },
  { title: 'August', content: ['cctv footage with u '], image: '/photos/august.jpg' },
  { title: 'September', content: ['school event nyo tas nag pic us'], image: '/photos/september.jpg' },
  { title: 'October', content: ['ur gala na di moko sinama huhu'], image: '/photos/october.jpg' },
  { title: 'November', content: ['pic mo sa phone ko nong may school event'], image: '/photos/november.jpg' },
  { title: 'December', content: ['bd ko na libre moko kase wala akong pera'], image: '/photos/december.jpg' },
  { title: 'January', content: ['sinundo kita sa pier nong uwi mo'], image: '/photos/january2026.jpg' },
  { title: 'February', content: ['Valentines Day <3'], image: '/photos/february2026.jpg' },
];
const page = ref(0);

function nextPage() {
  if (page.value < pages.length - 1) page.value++;
}
function prevPage() {
  if (page.value > 0) page.value--;
}
</script>

<template>
  <div class="book">
    <div class="page">
      <h1>{{ pages[page].title }}</h1>
      <template v-if="pages[page].image">
        <div class="img-page">
          <img :src="pages[page].image" alt="Memory" />
          <p v-if="pages[page].content && pages[page].content.length" class="img-caption">{{ pages[page].content[0] }}</p>
        </div>
      </template>
      <template v-else>
        <template v-for="(line, idx) in pages[page].content" :key="idx">
          <p v-if="page === 0 && idx === 0" class="main-message">{{ line }}</p>
          <p v-else-if="page === 0 && idx === 2" class="signature">{{ line }}</p>
          <p v-else-if="page === 0 && idx === 3" class="signature-name">{{ line }}</p>
          <p v-else>{{ line }}</p>
        </template>
      </template>
      <div class="nav">
        <button @click="prevPage" :disabled="page === 0">&#8592; Prev</button>
        <span class="page-num">Page {{ page + 1 }} / 13</span>
        <button @click="nextPage" :disabled="page === pages.length - 1">Next &#8594;</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.main-message {
  font-size: 1.1em;
  color: #b04848;
  margin-bottom: 18px;
  text-align: left;
  white-space: pre-line;
}
h1 {
  text-align: center;
  font-size: 2.2em;
  margin-bottom: 18px;
  color: #e75480;
  letter-spacing: 1px;
}
.signature {
  font-size: 1.1em;
  color: #e75480;
  margin-top: 24px;
  text-align: left;
  font-style: italic;
}
.signature-name {
  font-size: 1.2em;
  color: #b04848;
  margin-top: 6px;
  text-align: left;
  font-family: 'Brush Script MT', cursive;
}
.book {
  width: 100%;
  max-width: 420px;
  margin: 0 auto;
  background: linear-gradient(135deg, #ffe3f0 60%, #ffd6e0 100%);
  border-radius: 18px;
  box-shadow: 0 6px 32px rgba(231,84,128,0.10);
  padding: 36px 18px 32px 18px;
  font-family: 'Georgia', serif;
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 60vh;
}
.book::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 0;
  width: 320px;
  height: 320px;
  background: url('https://upload.wikimedia.org/wikipedia/commons/0/08/Red_rose_icon.svg') no-repeat center center;
  background-size: 180px 180px;
  opacity: 0.07;
  transform: translateX(-50%) translateY(-40px) rotate(-15deg);
  pointer-events: none;
}
.page {
  background: #fff0f5;
  border-radius: 12px;
  padding: 28px 10px;
  box-shadow: 0 2px 12px rgba(231,84,128,0.06);
}
.greeting {
  font-size: 1.1em;
  font-style: italic;
  margin-bottom: 12px;
}
.signature {
  margin-top: 32px;
  text-align: right;
  font-family: 'Brush Script MT', cursive;
  font-size: 1.2em;
  color: #e75480;
}
.img-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 320px;
}
.img-page img {
  max-width: 90%;
  max-height: 340px;
  border-radius: 16px;
  box-shadow: 0 4px 24px #e7548033;
  margin: 24px 0;
}
.img-caption {
  text-align: center;
  color: #e75480;
  font-size: 1.1em;
  margin-top: 8px;
  font-style: italic;
}
</style>
<style scoped>
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 24px;
}
.nav button {
  background: #e75480;
  color: #fff;
  border: none;
  border-radius: 6px;
  padding: 8px 18px;
  font-size: 1em;
  cursor: pointer;
  transition: background 0.2s;
}
.nav button:disabled {
  background: #ffd6e0;
  color: #aaa;
  cursor: not-allowed;
}
.page-num {
  font-size: 1em;
  color: #e75480;
  font-weight: bold;
}
</style>
<style scoped>
@media (max-width: 600px) {
  .book {
    max-width: 98vw;
    padding: 10vw 2vw;
    min-height: 70vw;
  }
  .page {
    padding: 6vw 2vw;
  }
}
</style>

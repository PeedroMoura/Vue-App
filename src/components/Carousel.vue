<template>
  <motion.div 
    class="carousel"
    :initial="{ opacity: 0, y: 40 }"
    :enter="{ opacity: 1, y: 0, transition: { type: 'spring', stiffness: 120, damping: 18 } }"
  >
    <button class="carousel-btn left" @click="prev" aria-label="Anterior">
      <svg width="28" height="28" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M18 6L10 14L18 22" stroke="#fff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </button>
    <img :src="images[current]" class="carousel-img" alt="Imagem do carrossel" />
    <button class="carousel-btn right" @click="next" aria-label="Próximo">
      <svg width="28" height="28" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M10 6L18 14L10 22" stroke="#fff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </button>
  </motion.div>
</template>

<script setup>
import { ref } from 'vue'

const images = [
  'https://picsum.photos/id/1015/600/300',
  'https://picsum.photos/id/1016/600/300',
  'https://picsum.photos/id/1018/600/300'
]
const current = ref(0)

function next() {
  current.value = (current.value + 1) % images.length
}
function prev() {
  current.value = (current.value - 1 + images.length) % images.length
}
</script>

<style scoped>
.carousel {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 2rem 0;
  width: 100%;
  overflow-x: auto;
}
.carousel-img {
  width: 600px;
  max-width: 95vw;
  height: 300px;
  object-fit: cover;
  border-radius: 10px;
  margin: 0 1rem;
  box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  background: #eee;
}
.carousel-btn {
  background: linear-gradient(135deg, #274060 60%, #42b983 100%);
  color: #fff;
  border: none;
  font-size: 2.2rem;
  width: 56px;
  height: 56px;
  padding: 0;
  cursor: pointer;
  border-radius: 50%;
  box-shadow: 0 4px 16px rgba(39,64,96,0.18), 0 1.5px 4px rgba(66,185,131,0.10);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.2s, box-shadow 0.2s, transform 0.1s;
  outline: none;
  position: relative;
}
.carousel-btn:hover {
  background: linear-gradient(135deg, #42b983 80%, #274060 100%);
  box-shadow: 0 6px 20px rgba(66,185,131,0.18), 0 2px 8px rgba(39,64,96,0.10);
  transform: translateY(-2px) scale(1.07);
}
.carousel-btn:active {
  background: linear-gradient(135deg, #274060 80%, #42b983 100%);
  box-shadow: 0 2px 8px rgba(39,64,96,0.18);
  transform: scale(0.96);
}
@media (max-width: 700px) {
  .carousel-img {
    width: 100vw;
    max-width: 350px;
    height: 160px;
  }
  .carousel {
    margin: 1.2rem 0;
  }
}
</style> 
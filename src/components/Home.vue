<template>
  <div class="home-bg">
    <Header />
    <motion.div
      class="motion-test"
      :initial="{ opacity: 0, scale: 0.5, rotate: 0 }"
      :enter="{ opacity: 1, scale: 1, rotate: 360, transition: { duration: 1.2, type: 'spring' } }"
    >
      Teste de Animação
    </motion.div>
    <main class="main-content">
      <motion.section class="hero"
        :initial="{ opacity: 0, y: 40 }"
        :enter="{ opacity: 1, y: 0, transition: { delay: 0.1, type: 'spring', stiffness: 120, damping: 18 } }"
      >
        <h1>Transforme sua presença digital</h1>
        <p class="subtitle">Desenvolvemos soluções web modernas, responsivas e sob medida para o seu negócio crescer.</p>
        <motion.div class="btn-group"
          :initial="{ opacity: 0, y: 20 }"
          :enter="{ opacity: 1, y: 0, transition: { delay: 0.25, type: 'spring', stiffness: 120, damping: 18 } }"
        >
          <button class="main-btn">Solicitar Orçamento</button>
          <button class="main-btn secondary">Fale Conosco</button>
        </motion.div>
      </motion.section>
      <Carousel />
      <motion.section class="about" id="sobre"
        :initial="{ opacity: 0, y: 40 }"
        :enter="{ opacity: 1, y: 0, transition: { delay: 0.35, type: 'spring', stiffness: 120, damping: 18 } }"
      >
        <h2>Sobre Nós</h2>
        <p>Somos uma equipe apaixonada por tecnologia, focada em criar experiências digitais inovadoras e eficientes. Atuamos com desenvolvimento web, design responsivo e soluções personalizadas para empresas de todos os portes.</p>
      </motion.section>
      <motion.section class="differentials" id="diferenciais"
        :initial="{ opacity: 0, y: 40 }"
        :enter="{ opacity: 1, y: 0, transition: { delay: 0.45, type: 'spring', stiffness: 120, damping: 18 } }"
      >
        <h2>Nossos Diferenciais</h2>
        <ul>
          <li><span>✔</span> Atendimento personalizado e consultivo</li>
          <li><span>✔</span> Design moderno e responsivo</li>
          <li><span>✔</span> Performance e segurança</li>
          <li><span>✔</span> Suporte dedicado</li>
        </ul>
      </motion.section>
      <motion.section class="img-section"
        :initial="{ opacity: 0, y: 40 }"
        :enter="{ opacity: 1, y: 0, transition: { delay: 0.55, type: 'spring', stiffness: 120, damping: 18 } }"
      >
        <img src="https://picsum.photos/id/1025/400/200" alt="Exemplo 1" />
        <img src="https://picsum.photos/id/1024/400/200" alt="Exemplo 2" />
      </motion.section>
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Header from './Header.vue'
import Footer from './Footer.vue'
import Carousel from './Carousel.vue'

</script>

<style scoped>
.home-bg {
  min-height: 100vh;
  background: linear-gradient(120deg, #f8fafc 60%, #e6f9f2 100%);
  display: flex;
  flex-direction: column;
}
.main-content {
  flex: 1;
  padding: 3rem 1rem 2rem 1rem;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
}
.hero {
  margin-bottom: 2.5rem;
}
h1 {
  font-size: 2.8rem;
  margin-bottom: 0.5rem;
  font-weight: bold;
  color: #274060;
  letter-spacing: 1px;
}
.subtitle {
  color: #555;
  font-size: 1.25rem;
  margin-bottom: 2rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}
.btn-group {
  margin: 2rem 0 2.5rem 0;
  display: flex;
  gap: 1.2rem;
  justify-content: center;
}
.main-btn {
  background: #42b983;
  color: #fff;
  border: none;
  padding: 0.85rem 2.2rem;
  border-radius: 6px;
  font-size: 1.15rem;
  cursor: pointer;
  transition: background 0.2s, transform 0.2s, box-shadow 0.2s;
  font-weight: 600;
  box-shadow: 0 2px 12px rgba(66,185,131,0.10);
  outline: none;
}
.main-btn:hover {
  background: #369870;
  transform: translateY(-2px) scale(1.04);
  box-shadow: 0 4px 18px rgba(66,185,131,0.18);
}
.main-btn.secondary {
  background: #274060;
  color: #fff;
}
.main-btn.secondary:hover {
  background: #18314a;
}
.about, .differentials {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 2px 12px rgba(39,64,96,0.06);
  padding: 2rem 1.5rem;
  margin: 2.5rem 0 1.5rem 0;
  width: 100%;
  max-width: 800px;
  text-align: left;
}
.about h2, .differentials h2 {
  color: #274060;
  font-size: 2rem;
  margin-bottom: 1rem;
}
.about p {
  color: #444;
  font-size: 1.15rem;
}
.differentials ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
.differentials li {
  font-size: 1.1rem;
  color: #222;
  margin-bottom: 0.7rem;
  display: flex;
  align-items: center;
  gap: 0.7rem;
}
.differentials li span {
  color: #42b983;
  font-size: 1.3rem;
}
.img-section {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 2rem;
  flex-wrap: wrap;
}
.img-section img {
  width: 350px;
  height: 180px;
  object-fit: cover;
  border-radius: 12px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.13);
  transition: transform 0.2s, box-shadow 0.2s;
  cursor: pointer;
}
.img-section img:hover {
  transform: scale(1.04) translateY(-4px);
  box-shadow: 0 6px 24px rgba(66,185,131,0.18);
}
.motion-test {
  width: 220px;
  height: 80px;
  background: linear-gradient(90deg, #42b983 60%, #274060 100%);
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.3rem;
  font-weight: bold;
  border-radius: 16px;
  margin: 2rem auto 1.5rem auto;
  box-shadow: 0 4px 24px rgba(39,64,96,0.18);
  letter-spacing: 1px;
}
@media (max-width: 900px) {
  .main-content {
    max-width: 100%;
    padding: 90px 0.5rem 70px 0.5rem;
  }
  .img-section img {
    width: 100%;
    max-width: 350px;
    height: 160px;
  }
  .about, .differentials {
    padding: 1.2rem 0.7rem;
  }
}
@media (max-width: 600px) {
  h1 {
    font-size: 2rem;
  }
  .img-section {
    flex-direction: column;
    gap: 1rem;
  }
  .img-section img {
    max-width: 100%;
    height: 120px;
  }
  .about, .differentials {
    padding: 1rem 0.2rem;
  }
}
</style> 
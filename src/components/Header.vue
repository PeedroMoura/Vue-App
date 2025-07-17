<template>
  <motion.header
    class="header"
    :initial="{ opacity: 0, y: -30 }"
    :enter="{ opacity: 1, y: 0, transition: { type: 'spring', stiffness: 120, damping: 18 } }"
  >
    <div class="header-content">
      <div class="logo">MeuSite</div>
      <div class="tagline">Soluções digitais para o seu negócio</div>
      <nav>
        <a href="#">Início</a>
        <a href="#sobre">Sobre</a>
        <a href="#diferenciais">Diferenciais</a>
        <a href="#contato">Contato</a>
      </nav>
    </div>
  </motion.header>
</template>

<script setup>
</script>

<style scoped>
.header {
  background: linear-gradient(90deg, #274060 60%, #42b983 100%);
  box-shadow: 0 2px 16px rgba(0,0,0,0.08);
}
.header-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0.7rem 2vw;
  width: 100%;
}
.logo {
  font-size: 2rem;
  font-weight: bold;
  color: #fff;
  letter-spacing: 1px;
}
.tagline {
  color: #e0e0e0;
  font-size: 1.1rem;
  margin-left: 2rem;
  font-style: italic;
  flex: 1;
}
nav {
  display: flex;
  gap: 2rem;
}
nav a {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  font-size: 1.1rem;
  transition: color 0.2s, border-bottom 0.2s;
  padding-bottom: 2px;
  border-bottom: 2px solid transparent;
}
nav a:hover {
  color: #42b983;
  border-bottom: 2px solid #42b983;
}
@media (max-width: 900px) {
  .header-content {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.3rem;
    padding: 0.7rem 1vw;
  }
  .tagline {
    margin-left: 0;
    font-size: 1rem;
  }
  nav {
    gap: 1.2rem;
  }
}
@media (max-width: 600px) {
  .logo {
    font-size: 1.3rem;
  }
  .tagline {
    font-size: 0.95rem;
  }
  nav a {
    font-size: 1rem;
  }
}
</style> 
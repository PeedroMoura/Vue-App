<template>
  <motion.footer
    class="footer"
    :initial="{ opacity: 0, y: 30 }"
    :enter="{ opacity: 1, y: 0, transition: { type: 'spring', stiffness: 120, damping: 18 } }"
  >
    <div class="footer-content">
      <div class="footer-left">
        <p>&copy; 2024 MeuSite. Todos os direitos reservados.</p>
        <p class="footer-desc">Desenvolvido por especialistas em soluções web.</p>
      </div>
      <div class="footer-links">
        <a href="#sobre">Sobre</a>
        <a href="#diferenciais">Diferenciais</a>
        <a href="#contato">Contato</a>
      </div>
    </div>
  </motion.footer>
</template>

<script setup>
</script>

<style scoped>
.footer {
  background: linear-gradient(90deg, #274060 60%, #42b983 100%);
  color: #fff;
  box-shadow: 0 -2px 16px rgba(0,0,0,0.08);
}
.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.7rem 2vw;
  width: 100%;
}
.footer-left {
  display: flex;
  flex-direction: column;
  gap: 0.2rem;
}
.footer-desc {
  font-size: 0.95rem;
  color: #e0e0e0;
}
.footer-links {
  display: flex;
  gap: 1.5rem;
}
.footer-links a {
  color: #fff;
  text-decoration: none;
  font-size: 1.05rem;
  transition: color 0.2s;
}
.footer-links a:hover {
  color: #42b983;
}
@media (max-width: 900px) {
  .footer-content {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
    padding: 0.7rem 1vw;
  }
  .footer-links {
    gap: 1rem;
  }
}
@media (max-width: 600px) {
  .footer-content {
    font-size: 0.95rem;
  }
  .footer-links a {
    font-size: 0.95rem;
  }
}
</style> 
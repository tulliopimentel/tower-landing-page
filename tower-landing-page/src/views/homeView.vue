<template>
  <div class="landing-page">
    <header class="header">
      <div class="container">
        <div class="logo">
          <img src="@/assets/TOWER-PERFIL.png" alt="Logo da Empresa de Edição de Vídeo" />
        </div>
        <button class="hamburger-menu" :class="{ 'is-open': isMenuOpen }" @click="toggleMenu" aria-label="Abrir Menu">
          <span class="bar"></span>
          <span class="bar"></span>
          <span class="bar"></span>
        </button>
        <nav class="main-nav" :class="{ 'is-open': isMenuOpen }">
          <ul>
            <li><a href="#home" @click="closeMenu">Home</a></li>
            <li><a href="#services" @click="closeMenu">Serviços</a></li>
            <li><a href="#about" @click="closeMenu">Quem somos nós</a></li>
            <li><a href="#portfolio" @click="closeMenu">Portfólio</a></li>
            <li><a href="#testimonials" @click="closeMenu">Depoimentos</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <div class="mobile-menu-overlay" :class="{ 'is-open': isMenuOpen }" @click="closeMenu"></div>

    <main class="hero-section">
      <div class="container">
        <h1 class="hero-title">Dê vida aos seus vídeos</h1>
        <p class="hero-subtitle">
       <span class="highlight">Se preocupe somente em gravar</span> e deixe o resto com a gente.
        </p>
        <div class="hero-actions">
          <a href="#contact" class="btn btn-primary">SOLICITAR ORÇAMENTO</a>
          <a href="#portfolio" class="btn btn-secondary">VER PORTFÓLIO</a>
        </div>
        <div class="company-logos">
          <p>Escolhida por diversos influencers e youtubers</p>
          <div class="logos-grid">
            <div class="placeholder-logo">LOGO 1</div>
            <div class="placeholder-logo">LOGO 2</div>
            <div class="placeholder-logo">LOGO 3</div>
            <div class="placeholder-logo">LOGO 4</div>
            <div class="placeholder-logo">LOGO 5</div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import { defineComponent, ref, watch } from 'vue'; // Importe 'watch' aqui
import '../styles/home.css';

export default defineComponent({
  name: 'HomeView',
  setup() {
    const isMenuOpen = ref(false);

    // Adicione um watcher para monitorar isMenuOpen
    watch(isMenuOpen, (newValue, oldValue) => {
      console.log('isMenuOpen CHANGED:', oldValue, '->', newValue);
    });

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
      console.log('Hamburger clicked! isMenuOpen state:', isMenuOpen.value);
      if (isMenuOpen.value) {
        document.body.classList.add('no-scroll');
      } else {
        document.body.classList.remove('no-scroll');
      }
    };

    const closeMenu = () => {
      isMenuOpen.value = false;
      document.body.classList.remove('no-scroll');
      console.log('Overlay or menu item clicked! isMenuOpen state:', isMenuOpen.value);
    };

    return {
      isMenuOpen,
      toggleMenu,
      closeMenu,
    };
  },
});
</script>
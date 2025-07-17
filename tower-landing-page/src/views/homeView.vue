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
      <div class="hero-container">
        <div class="hero-text">
          <h1 class="hero-title">Dê vida aos seus vídeos</h1>
          <p class="hero-subtitle">
            <span class="highlight">Se preocupe somente em gravar</span> e deixe o resto com a gente.
          </p>
          <div class="hero-actions">
            <a href="#contact" class="btn btn-primary">SOLICITAR ORÇAMENTO</a>
            <a href="#portfolio" class="btn btn-secondary">VER PORTFÓLIO</a>
          </div>
        </div>
        <div class="hero-image">
          <img src="@/assets/TOWER-PERFIL.png" alt="Imagem da Torre Perfil" />
        </div>
      </div>
      <div class="company-logos">
        <p>Escolhida por diversos influencers e youtubers</p>
        <swiper-container
          :slides-per-view="swiperOptions.slidesPerView"
          :space-between="swiperOptions.spaceBetween"
          :loop="swiperOptions.loop"
          :autoplay="swiperOptions.autoplay"
          :pagination="swiperOptions.pagination"
          :navigation="swiperOptions.navigation"
          :breakpoints="swiperOptions.breakpoints"
          class="logos-carousel"
        >
          <swiper-slide v-for="(person, index) in people" :key="index">
            <div class="logo-item">
              <img :src="person.image" :alt="person.alt" class="company-logo" />
              <span class="logo-name">{{ person.name }}</span>
            </div>
          </swiper-slide>
          </swiper-container>
      </div>
    </main>
  </div>
</template>

<script>
import { defineComponent, ref, watch } from 'vue';
import { register } from 'swiper/element/bundle'; // Importa o registro dos web components
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

import '../styles/home.css';

// Registra todos os elementos Swiper, incluindo swiper-container, swiper-slide
register();

export default defineComponent({
  name: 'HomeView',
  setup() {
    const isMenuOpen = ref(false);

    // O console.log do watch pode ser removido após a depuração
    watch(isMenuOpen, (newValue) => {
      console.log('isMenuOpen CHANGED:', newValue);
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

    const people = [
      { image: new URL('@/assets/super_xandao.png', import.meta.url).href, alt: 'Foto Super Xandão', name: 'Super Xandão' },
      { image: new URL('@/assets/victor_sarro.png', import.meta.url).href, alt: 'Foto Victor Sarro', name: 'Victor Sarro' },
      { image: new URL('@/assets/anna_egreja.jpg', import.meta.url).href, alt: 'Foto Anna Egreja', name: 'Anna Egreja' },
      { image: new URL('@/assets/gorgonoide.jpg', import.meta.url).href, alt: 'Foto Gorgonoide', name: 'Gorgonoid' },
      { image: new URL('@/assets/tinows.jpg', import.meta.url).href, alt: 'Foto Tinows', name: 'Tinowns' }
    ];

    const swiperOptions = {
      slidesPerView: 5,
      spaceBetween: 30,
      loop: true,
      autoplay: {
        delay: 3000,
        disableOnInteraction: false,
      },
      pagination: {
        el: '.swiper-pagination', // O Swiper procurará por este elemento no DOM, ele o criará se não existir.
        clickable: true,
      },
      navigation: {
        nextEl: '.swiper-button-next', // O Swiper procurará por este elemento no DOM, ele o criará se não existir.
        prevEl: '.swiper-button-prev',
      },
      breakpoints: {
        1200: {
          slidesPerView: 5,
          spaceBetween: 30,
        },
        992: {
          slidesPerView: 4,
          spaceBetween: 20,
        },
        768: {
          slidesPerView: 3,
          spaceBetween: 20,
        },
        576: {
          slidesPerView: 2,
          spaceBetween: 15,
        },
        0: {
          slidesPerView: 1,
          spaceBetween: 10,
        },
      },
    };

    return {
      isMenuOpen,
      toggleMenu,
      closeMenu,
      people,
      swiperOptions,
    };
  },
});
</script>
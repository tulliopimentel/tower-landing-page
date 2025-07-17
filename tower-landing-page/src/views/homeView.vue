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

      <div class="impact-cards">
        <div class="impact-card">
          <span class="impact-number">+100 Milhões</span>
          <span class="impact-description">de visualizações</span>
        </div>
        <div class="impact-card">
          <span class="impact-number">+1000</span>
          <span class="impact-description">vídeos editados</span>
        </div>
        <div class="impact-card">
          <span class="impact-number">+50</span>
          <span class="impact-description">clientes satisfeitos</span>
        </div>
          <div class="impact-card">
          <span class="impact-number">+4 anos</span>
          <span class="impact-description">de mercado</span>
        </div>
      </div>
      <div class="company-logos">
        <p>Parceiros que brilham: Conheça quem já confia em nosso trabalho. E muito mais!</p>
        <swiper-container
          :slides-per-view="swiperOptions.slidesPerView"
          :space-between="swiperOptions.spaceBetween"
          :loop="swiperOptions.loop"
          :autoplay="swiperOptions.autoplay"
          :pagination="swiperOptions.pagination"
          :navigation="swiperOptions.navigation"
          :free-mode="swiperOptions.freeMode"
          :speed="swiperOptions.speed"
          :allow-touch-move="swiperOptions.allowTouchMove"
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

      <section class="services-section" id="services">
        <p class="section-tag">/ SERVIÇOS /</p>
        <h2 class="section-title">
          Soluções <span class="highlight">completas</span> para o seu conteúdo, do conceito à entrega.
        </h2>
        <div class="services-grid">
          <div class="service-card">
            <h3 class="service-card-title">Edição de Vídeo</h3>
            <p class="service-card-description">
              Transformamos suas ideias em narrativas visuais <span class="highlight">cativantes</span>, com cortes precisos e efeitos impactantes para ser publicado em qualquer formato nas redes sociais.
            </p>
          </div>
          <div class="service-card">
            <h3 class="service-card-title">Gravações</h3>
            <p class="service-card-description">
              Capturamos a <span class="highlight">essência</span> da sua mensagem, seja com equipamentos profissionais em solo ou imagens aéreas de drone.
            </p>
          </div>
          <div class="service-card">
            <h3 class="service-card-title">Motion Graphics & Ilustração</h3>
            <p class="service-card-description">
              Damos vida à sua marca com animações e <span class="highlight">ilustrações criativas</span>, tornando vídeos complexos em experiências visuais claras.
            </p>
          </div>
          <div class="service-card">
            <h3 class="service-card-title">Planejamento & Roteiro</h3>
            <p class="service-card-description">
              Desenvolvemos o <span class="highlight">roteiro</span> ideal e um planejamento estratégico para cada etapa do seu projeto de vídeo, do conceito à entrega final.
            </p>
          </div>
        </div>
      </section>

      <section class="about-us-section" id="about">
        <div class="about-content">
          <div class="about-image">
            <img src="@/assets/fer.jpg" alt="Foto da equipe ou fundadores" />
          </div>
          <div class="about-text">
            <p class="section-tag">/ QUEM SOMOS NÓS /</p>
            <h2 class="section-title">
              Uma história de <span class="highlight">paixão</span> e superação pelo conteúdo digital.
            </h2>
            <p>
              Nossa jornada não começou em escritórios de luxo, mas nas ruas, observando o mundo sob uma perspectiva única. Foi lá, em meio à resiliência e à criatividade forçada pela necessidade, que percebemos o poder das histórias e como o vídeo poderia amplificá-las. Com uma câmera emprestada e uma paixão ardente por transformar o ordinário em extraordinário, **Maria e João**, como que por obra do destino, se uniram.
            </p>
            <p>
              De cada dificuldade, tiramos um aprendizado; de cada recurso limitado, uma solução engenhosa. Essa vivência nos ensinou a valorizar a essência, a capturar a verdade e a criar com propósito. Hoje, a Tower Content é o reflexo dessa jornada: uma agência de conteúdo digital que entende a importância de cada história e o impacto real que um vídeo bem feito pode ter.
            </p>
            <p>
              Não vendemos apenas vídeos; construímos <span class="highlight">pontes</span>, geramos conexões e transformamos sonhos em realidade digital. Sua história merece ser contada com a mesma dedicação e visão que nos trouxeram até aqui.
            </p>
          </div>
        </div>
      </section>

      <section class="portfolio-section" id="portfolio">
        <div class="portfolio-header">
          <p class="section-tag">/ PORTFÓLIO /</p>
          <div class="parallax-title-wrapper" ref="parallaxTitleWrapper">
            <h2 class="section-title portfolio-title" ref="portfolioTitle">
              Confira alguns dos projetos produzidos pela <span class="highlight">Tower Content</span>
            </h2>
          </div>
        </div>

        <div class="portfolio-content">
          <p class="portfolio-description">
            Na Tower Content, transformamos a visão de youtubers e influencers em realidade visual que <span class="highlight">engaja e converte</span>. Cada projeto é uma fusão de técnica apurada e storytelling estratégico, elevando a qualidade do seu conteúdo para além das expectativas. Seja para um vídeo de alta produção, um compilado dinâmico ou um formato inovador, nossa expertise garante vídeos que não apenas atraem milhões de visualizações, mas também fortalecem sua marca e conectam profundamente com sua audiência. Deixe a edição conosco e foque no que você faz de melhor: criar!
          </p>

          <div class="portfolio-videos">
            <h3 class="portfolio-videos-title">Portfolio</h3>
            <div class="video-responsive">
              <iframe
                src="https://www.youtube.com/embed/jfKfPfyqkOY?autoplay=1&mute=1&loop=1&playlist=jfKfPfyqkOY&controls=1"
                title="YouTube video player - LoFi Girl"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen>
              </iframe>
            </div>
            </div>
        </div>
      </section>
      </main>
  </div>
</template>

<script>
import { defineComponent, ref, watch, onMounted, onUnmounted } from 'vue';
import { register } from 'swiper/element/bundle';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/free-mode';

import '../styles/home.css';

register();

export default defineComponent({
  name: 'HomeView',
  setup() {
    const isMenuOpen = ref(false);
    const portfolioTitle = ref(null);
    const parallaxTitleWrapper = ref(null);

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

    const handleScroll = () => {
      if (portfolioTitle.value && parallaxTitleWrapper.value) {
        const scrollY = window.scrollY;
        const sectionRect = parallaxTitleWrapper.value.getBoundingClientRect();
        const sectionTop = sectionRect.top + scrollY;
        const sectionHeight = sectionRect.height;

        const viewportHeight = window.innerHeight;
        const startScroll = sectionTop - viewportHeight;
        const endScroll = sectionTop + sectionHeight;

        if (scrollY > startScroll && scrollY < endScroll) {
          const scrollProgress = (scrollY - startScroll) / (endScroll - startScroll);
          const parallaxSpeed = 0.3;
          const translateY = scrollProgress * 50 * parallaxSpeed;
          portfolioTitle.value.style.transform = `translateY(${translateY}px)`;
        } else if (scrollY <= startScroll) {
          portfolioTitle.value.style.transform = `translateY(0px)`;
        } else if (scrollY >= endScroll) {
          const parallaxOffsetAtEnd = (endScroll - startScroll) / (endScroll - startScroll) * 50 * parallaxSpeed;
          portfolioTitle.value.style.transform = `translateY(${parallaxOffsetAtEnd}px)`;
        }
      }
    };

    onMounted(() => {
      window.addEventListener('scroll', handleScroll);
    });

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll);
    });

    const people = [
      { image: new URL('@/assets/super_xandao.png', import.meta.url).href, alt: 'Foto Super Xandão', name: 'Super Xandão' },
      { image: new URL('@/assets/victor_sarro.png', import.meta.url).href, alt: 'Foto Victor Sarro', name: 'Victor Sarro' },
      { image: new URL('@/assets/anna_egreja.jpg', import.meta.url).href, alt: 'Foto Anna Egreja', name: 'Anna Egreja' },
      { image: new URL('@/assets/gorgonoide.jpg', import.meta.url).href, alt: 'Foto Gorgonoide', name: 'Gorgonoid' },
      { image: new URL('@/assets/tinows.jpg', import.meta.url).href, alt: 'Foto Tinows', name: 'Tinowns' },
      { image: new URL('@/assets/ericat.jpg', import.meta.url).href, alt: 'Foto Ericat', name: 'Ericat' },
      { image: new URL('@/assets/gabriel_curiosidades.png', import.meta.url).href, alt: 'Foto Gabriel', name: 'Gabriel Chinchilla Curiosidades' },
      { image: new URL('@/assets/snickers.png', import.meta.url).href, alt: 'Foto Snickers', name: 'Snickers' },
      { image: new URL('@/assets/vivo_cliente.jpg', import.meta.url).href, alt: 'Foto Vivo', name: 'Vivo' },
    ];

    const swiperOptions = {
      slidesPerView: 5,
      spaceBetween: 30,
      loop: true,
      allowTouchMove: true,
      speed: 10000,

      autoplay: {
        delay: 0,
        disableOnInteraction: false,
        reverseDirection: false,
      },

      freeMode: {
        enabled: true,
        sticky: false,
        momentum: false,
      },

      pagination: {
        el: '.swiper-pagination',
        clickable: true,
      },
      navigation: {
        nextEl: '.swiper-button-next',
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
          slidesPerView: 2,
          spaceBetween: 0
        },
      },
    };

    return {
      isMenuOpen,
      toggleMenu,
      closeMenu,
      people,
      swiperOptions,
      portfolioTitle,
      parallaxTitleWrapper
    };
  },
});
</script>
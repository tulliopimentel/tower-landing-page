<template>
  <div class="landing-page" id="home">
    <header class="header">
      <div class="container">
        <a href="#home" class="logo" aria-label="Voltar para o início - Logotipo Tower Studio">
          <img src="@/assets/TOWER-PERFIL.png" alt="Tower Studio - Edição de Vídeos, Gravações e Motion Graphics" loading="lazy" width="150" height="50"/>
        </a>
        <button class="hamburger-menu" :class="{ 'is-open': isMenuOpen }" @click="toggleMenu" aria-label="Abrir Menu de Navegação">
          <span class="bar"></span>
          <span class="bar"></span>
          <span class="bar"></span>
        </button>
        <nav class="main-nav" :class="{ 'is-open': isMenuOpen }" aria-label="Navegação Principal do Site">
          <ul>
            <li><a href="#home" @click="closeMenu" aria-label="Ir para a seção Início">Início</a></li>
            <li><a href="#services" @click="closeMenu" aria-label="Ir para a seção Serviços">Serviços</a></li>
            <li><a href="#about" @click="closeMenu" aria-label="Ir para a seção Quem Somos">Quem Somos</a></li>
            <li><a href="#portfolio" @click="closeMenu" aria-label="Ir para a seção Portfólio">Portfólio</a></li>
            <li><a href="#testimonials" @click="closeMenu" aria-label="Ir para a seção Depoimentos">Depoimentos</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <main class="hero-section">
      <div class="hero-container">
        <div class="hero-text">
          <h1 class="hero-title">Dê vida aos seus vídeos</h1>
          <p class="hero-subtitle">
            <span class="highlight">Se preocupe somente em gravar,</span> e deixe a Edição Profissional com a gente!
          </p>
          <div class="hero-actions">
            <a href="https://wa.me/5518997762278?text=Olá, gostaria de solicitar um orçamento para edição de video" target="_blank" class="btn btn-primary" rel="noopener noreferrer" title="Solicitar Orçamento de Edição de Vídeo via WhatsApp">
              SOLICITAR ORÇAMENTO
            </a>
            <a href="#portfolio" class="btn btn-secondary" title="Ver Portfólio de Vídeos Editados">VER PORTFÓLIO</a>
          </div>
        </div>
        <div class="hero-image">
          <img src="@/assets/TOWER-PERFIL.png" alt="Editor de vídeo profissional trabalhando em projeto de edição para YouTube e Redes Sociais - Tower Studio" loading="eager" width="600" height="400" />
        </div>
      </div>

      <section class="impact-cards" aria-labelledby="impact-stats-title">
        <h2 id="impact-stats-title" class="sr-only">Nossos Resultados e Impacto</h2>
        <div class="impact-card">
          <span class="impact-number">+100 Milhões</span>
          <span class="impact-description">de visualizações alcançadas para nossos clientes</span>
        </div>
        <div class="impact-card">
          <span class="impact-number">+1000</span>
          <span class="impact-description">vídeos editados e entregues com sucesso</span>
        </div>
        <div class="impact-card">
          <span class="impact-number">+50</span>
          <span class="impact-description">clientes satisfeitos com nossos serviços</span>
        </div>
        <div class="impact-card">
          <span class="impact-number">+4 anos</span>
          <span class="impact-description">de experiência no mercado de conteúdo digital</span>
        </div>
      </section>

      <section class="company-logos" aria-labelledby="partners-title">
        <h2 id="partners-title" class="section-title">Parceiros que brilham: Conheça quem já confia em nosso trabalho. E muito mais!</h2>
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
          aria-live="polite"
        >
          <swiper-slide v-for="(person, index) in people" :key="index">
            <div class="logo-item">
              <img :src="person.image" :alt="person.alt" class="company-logo" loading="lazy" width="100" height="100" />
              <span class="logo-name">{{ person.name }}</span>
            </div>
          </swiper-slide>
        </swiper-container>
      </section>

      <section class="services-section" id="services" aria-labelledby="services-title">
        <p class="section-tag">/ NOSSOS SERVIÇOS /</p>
        <h2 id="services-title" class="section-title">
          Soluções <span class="highlight">completas</span> para o seu conteúdo digital: edição, gravação, motion graphics e planejamento.
        </h2>
        <div class="services-grid">
          <article class="service-card">
            <h3 class="service-card-title">Edição de Vídeo Profissional</h3>
            <p class="service-card-description">
              Transformamos suas ideias em narrativas visuais <span class="highlight">cativantes</span>, com cortes precisos e efeitos impactantes para ser publicado em qualquer formato nas redes sociais, YouTube, Instagram, TikTok e mais.
            </p>
          </article>
          <article class="service-card">
            <h3 class="service-card-title">Gravações de Alta Qualidade</h3>
            <p class="service-card-description">
              Capturamos a <span class="highlight">essência</span> da sua mensagem, seja com equipamentos profissionais em solo ou imagens aéreas espetaculares de drone, garantindo a melhor qualidade para seu projeto.
            </p>
          </article>
          <article class="service-card">
            <h3 class="service-card-title">Motion Graphics & Ilustração Animada</h3>
            <p class="service-card-description">
              Damos vida à sua marca com animações e <span class="highlight">ilustrações criativas</span>, tornando vídeos complexos em experiências visuais claras, dinâmicas e memoráveis.
            </p>
          </article>
          <article class="service-card">
            <h3 class="service-card-title">Planejamento Estratégico & Roteiro de Vídeo</h3>
            <p class="service-card-description">
              Desenvolvemos o <span class="highlight">roteiro</span> ideal e um planejamento estratégico detalhado para cada etapa do seu projeto de vídeo, do conceito inicial à entrega final, otimizando o impacto.
            </p>
          </article>
        </div>
        <div class="services-cta">
          <a href="https://wa.me/5518997762278?text=Olá, gostaria de solicitar um orçamento para edição de video" target="_blank" class="btn btn-primary" rel="noopener noreferrer" title="Fale Conosco para Orçamento de Serviços de Vídeo">
            SOLICITAR ORÇAMENTO AGORA
          </a>
        </div>
      </section>

      <section class="about-us-section" id="about" aria-labelledby="about-title">
        <div class="about-content">
          <div class="about-image">
            <img src="@/assets/TOWER-PERFIL.png" alt="Guilherme e Gabriel, fundadores da Tower Studio, equipe especializada em produção de conteúdo digital" loading="lazy" width="600" height="400" />
          </div>
          <div class="about-text">
            <p class="section-tag">/ QUEM SOMOS NÓS /</p>
            <h2 id="about-title" class="section-title">
              Uma história de <span class="highlight">paixão</span>, superação e expertise em conteúdo digital.
            </h2>
           <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
          </p>
          <p>
            Curabitur pretium tincidunt lacus. Nulla gravida <span class="highlight">orci</span> a odio. Nullam varius, turpis et commodo pharetra, est eros bibendum elit, nec luctus magna felis sollicitudin mauris. Integer in mauris eu nibh egestas ultricies. Aenean a dolor et sapien <span class="highlight">placerat</span> sagittis.
          </p>
          <p>
            Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu <span class="highlight">libero</span> sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo. Quisque sit amet est et sapien ullamcorper pharetra. Ut varius tincidunt libero.
          </p>
          </div>
        </div>
      </section>

      <section class="portfolio-section" id="portfolio" aria-labelledby="portfolio-title">
        <div class="portfolio-header">
          <p class="section-tag">/ NOSSO PORTFÓLIO /</p>
          <div class="parallax-title-wrapper" ref="parallaxTitleWrapper">
            <h2 id="portfolio-title" class="section-title portfolio-title" ref="portfolioTitle">
              Confira alguns dos projetos de sucesso produzidos pela <span class="highlight">Tower Studio</span>
            </h2>
          </div>
        </div>

        <div class="portfolio-content">
          <p class="portfolio-description">
            Na Tower Studio, transformamos a visão de youtubers e influencers em realidade visual que <span class="highlight">engaja e converte</span>. Cada projeto é uma fusão de técnica apurada e storytelling estratégico, elevando a qualidade do seu conteúdo para além das expectativas. Seja para um vídeo de alta produção, um compilado dinâmico ou um formato inovador, nossa expertise garante vídeos que não apenas atraem milhões de visualizações, mas também fortalecem sua marca e conectam profundamente com sua audiência. Deixe a edição conosco e foque no que você faz de melhor: criar!
          </p>

          <div class="portfolio-videos">
            <h3 class="portfolio-videos-title">Portfolio</h3>
            <div class="video-responsive">
              <iframe
                src="https://www.youtube.com/embed/9Fsa0_uuaDM"
                title="Melhores momentos de edição de vídeo - Portfólio Tower Studio"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen
                loading="lazy"
              ></iframe>
            </div>
          </div>
        </div>
      </section>

      <section class="testimonials-section" id="testimonials" aria-labelledby="testimonials-title">
        <p class="section-tag">/ O QUE DIZEM NOSSOS CLIENTES /</p>
        <h2 id="testimonials-title" class="section-title">
          Vozes que <span class="highlight">inspiram</span>: Depoimentos de quem já colhe resultados com a Tower Studio.
        </h2>
        <swiper-container
          :slides-per-view="testimonialsSwiperOptions.slidesPerView"
          :space-between="testimonialsSwiperOptions.spaceBetween"
          :loop="testimonialsSwiperOptions.loop"
          :autoplay="testimonialsSwiperOptions.autoplay"
          :pagination="testimonialsSwiperOptions.pagination"
          :navigation="testimonialsSwiperOptions.navigation"
          :grab-cursor="true"
          class="testimonials-carousel"
          aria-live="polite"
        >
          <swiper-slide v-for="(testimonial, index) in testimonials" :key="index">
            <article class="testimonial-card">
              <div class="testimonial-header">
                <img :src="testimonial.avatar" :alt="testimonial.name" class="testimonial-avatar" loading="lazy" width="80" height="80" />
                <div class="testimonial-info">
                  <h3 class="testimonial-name">{{ testimonial.name }}</h3>
                  <p class="testimonial-role">{{ testimonial.role }}</p>
                </div>
              </div>
              <p class="testimonial-text">{{ testimonial.text }}</p>
              <div class="testimonial-rating">
                <span v-for="star in testimonial.rating" :key="star" class="star">★</span>
              </div>
            </article>
          </swiper-slide>
        </swiper-container>
      </section>
      </main>

    <footer class="footer" aria-labelledby="footer-heading">
      <h2 id="footer-heading" class="sr-only">Informações de Contato e Navegação do Rodapé</h2>
      <div class="container">
        <div class="footer-brand">
          <img src="@/assets/TOWER-PERFIL.png" alt="Logo da Tower Studio - Edição de Vídeos" loading="lazy" width="100" height="30" />
          <p>Sua parceira em conteúdo digital de alta performance.</p>
        </div>
        <nav class="footer-nav" aria-label="Navegação do Rodapé">
          <ul>
            <li><a href="#home">Início</a></li>
            <li><a href="#services">Serviços</a></li>
            <li><a href="#about">Quem Somos</a></li>
            <li><a href="#portfolio">Portfólio</a></li>
            <li><a href="#testimonials">Depoimentos</a></li>
            <li><a href="mailto:contato@towerstudio.com" title="Envie um e-mail para a Tower Studio">contato@towerstudio.com</a></li>
            <li><a href="tel:+5518997762278" title="Ligue para a Tower Studio">+55 18 99776-2278</a></li>
          </ul>
        </nav>
        <div class="social-links">
          <p>Siga-nos nas redes sociais:</p>
          <ul>
            <li><a href="#" target="_blank" rel="noopener noreferrer" aria-label="Link para o Instagram da Tower Studio"><i class="fab fa-instagram"></i> Instagram</a></li>
            <li><a href="#" target="_blank" rel="noopener noreferrer" aria-label="Link para o YouTube da Tower Studio"><i class="fab fa-youtube"></i> YouTube</a></li>
            </ul>
        </div>
      </div>
      <div class="footer-bottom">
        <p>© {{ new Date().getFullYear() }} Tower Studio. Todos os direitos reservados.</p>
      </div>
    </footer>
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

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
      if (isMenuOpen.value) {
        document.body.classList.add('no-scroll');
      } else {
        document.body.classList.remove('no-scroll');
      }
    };

    const closeMenu = (event) => {
      const isNavLink = event && event.target && event.target.tagName === 'A' && event.target.closest('.main-nav');
      const href = isNavLink ? event.target.getAttribute('href') : null;
      
      if (isNavLink && href && href.startsWith('#')) {
        event.preventDefault();
        const targetElement = document.querySelector(href);
        if (targetElement) {
          const headerOffset = 105;
          const elementPosition = targetElement.getBoundingClientRect().top + window.scrollY;
          window.scrollTo({
            top: elementPosition - headerOffset,
            behavior: 'smooth'
          });
        }
      }

      isMenuOpen.value = false;
      document.body.classList.remove('no-scroll');

      if (isNavLink && href) {
        setTimeout(() => {
          if (href.startsWith('#')) {
            const targetElement = document.querySelector(href);
            if (targetElement) {
              const headerOffset = 105;
              const elementPosition = targetElement.getBoundingClientRect().top + window.scrollY;
              window.scrollTo({
                top: elementPosition - headerOffset,
                behavior: 'smooth'
              });
            }
          } else {
            window.location.href = href;
          }
        }, 300);
      }
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
      { image: new URL('@/assets/super_xandao.png', import.meta.url).href, alt: 'Super Xandão - Parceiro da Tower Studio', name: 'Super Xandão' },
      { image: new URL('@/assets/victor_sarro.png', import.meta.url).href, alt: 'Victor Sarro - Cliente da Tower Studio', name: 'Victor Sarro' },
      { image: new URL('@/assets/anna_egreja.jpg', import.meta.url).href, alt: 'Anna Egreja - Colaboradora da Tower Studio', name: 'Anna Egreja' },
      { image: new URL('@/assets/gorgonoide.jpg', import.meta.url).href, alt: 'Gorgonoid - Parceiro de conteúdo digital', name: 'Gorgonoid' },
      { image: new URL('@/assets/tinows.jpg', import.meta.url).href, alt: 'Tinowns - Profissional de eSports', name: 'Tinowns' },
      { image: new URL('@/assets/ericat.jpg', import.meta.url).href, alt: 'Ericat - Streamer e Influencer', name: 'Ericat' },
      { image: new URL('@/assets/gabriel_curiosidades.png', import.meta.url).href, alt: 'Gabriel Chinchilla - Criador de Conteúdo', name: 'Gabriel Chinchilla' },
      { image: new URL('@/assets/snickers.png', import.meta.url).href, alt: 'Snickers - Marca parceira', name: 'Snickers' },
      { image: new URL('@/assets/vivo_cliente.jpg', import.meta.url).href, alt: 'Vivo - Empresa de Telecomunicações', name: 'Vivo' },
    ];

    const testimonials = [
      {
        name: "Cláudio Junior",
        role: "YouTuber e Influencer",
        avatar: new URL('@/assets/avatar-claudio.jpg', import.meta.url).href, // Substitua pelo caminho da imagem
        text: "A Tower Studio transformou meus vídeos! A edição é impecável, com cortes que dão um ritmo incrível e efeitos que elevam a qualidade. Meus inscritos notaram a diferença, e o engajamento disparou. Recomendo demais para quem quer profissionalizar seu conteúdo!",
        rating: 5
      },
      {
        name: "Beatriz Costa",
        role: "CEO, Startup Tech",
        avatar: new URL('@/assets/avatar-beatriz.jpg', import.meta.url).href, // Substitua pelo caminho da imagem
        text: "Precisávamos de motion graphics que realmente transmitissem a inovação da nossa startup. A equipe da Tower Studio superou todas as expectativas! Criaram animações dinâmicas e claras que explicam nosso produto de forma genial. Profissionais e criativos!",
        rating: 5
      },
      {
        name: "Lucas Mendes",
        role: "Criador de Conteúdo Fitness",
        avatar: new URL('@/assets/avatar-lucas.jpg', import.meta.url).href, // Substitua pelo caminho da imagem
        text: "Com a Tower Studio, pude focar na gravação enquanto eles cuidavam de toda a pós-produção. O resultado? Vídeos com qualidade cinematográfica, que me posicionaram como autoridade no meu nicho. Se você busca excelência em edição, não procure mais!",
        rating: 4
      },
      {
        name: "Isabela Oliveira",
        role: "Marketing Manager, E-commerce",
        avatar: new URL('@/assets/avatar-isabela.jpg', import.meta.url).href, // Substitua pelo caminho da imagem
        text: "O planejamento estratégico de vídeo da Tower Studio foi um divisor de águas para nossa campanha. Eles entenderam perfeitamente nossos objetivos e entregaram um roteiro que converteu muito. Além da edição de altíssimo nível, o suporte e a comunicação são excelentes.",
        rating: 5
      }
    ];

    const swiperOptions = {
      slidesPerView: 5,
      spaceBetween: 30,
      loop: true,
      allowTouchMove: true,
      speed: 4000,

      autoplay: {
        delay: 0,
        disableOnInteraction: false,
        reverseDirection: false,
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
          slidesPerView: 3,
          spaceBetween: 15,
        },
        0: {
          slidesPerView: 3,
          spaceBetween: 0
        },
      },
    };

    const testimonialsSwiperOptions = {
      slidesPerView: 1, // Padrão para telas pequenas
      spaceBetween: 30,
      loop: true,
      allowTouchMove: true,
      speed: 4000,

      autoplay: {
        delay: 3000,
        disableOnInteraction: false,
        reverseDirection: false,
      },

      breakpoints: {
        // Para telas maiores que 992px (desktops), exibe 3 cards
        992: {
          slidesPerView: 1,
          spaceBetween: 30,
        },
        // Para telas entre 768px e 991px (tablets maiores), exibe 1 card
        768: {
          slidesPerView: 1,
          spaceBetween: 30,
        },
        // Para telas entre 576px e 767px (mobile paisagem), exibe 1 card
        576: {
          slidesPerView: 1,
          spaceBetween: 30,
        },
        // Para telas menores que 576px (mobile retrato), exibe 1 card
        0: {
          slidesPerView: 1,
          spaceBetween: 30
        },
      },
    };

    return {
      isMenuOpen,
      toggleMenu,
      closeMenu,
      people,
      swiperOptions,
      testimonials,
      testimonialsSwiperOptions,
      portfolioTitle,
      parallaxTitleWrapper
    };
  },
});
</script>
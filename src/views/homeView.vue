<template>
  <div class="landing-page" id="home">
    <header class="header" :class="{ 'is-scrolled': isHeaderScrolled }">
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
            <li class="mobile-cta">
              <a href="https://wa.me/5518997762278?text=Olá, quero impulsionar meus vídeos com a Tower!" target="_blank" rel="noopener" class="btn btn-primary" aria-label="Chamar WhatsApp">
                FALAR NO WHATSAPP
              </a>
            </li>
          </ul>
        </nav>
        <div class="header-cta">
          <a href="https://wa.me/5518997762278?text=Olá!%20Quero%20impulsionar%20meus%20vídeos.%20Pode%20me%20ajudar%3F" target="_blank" rel="noopener noreferrer" class="btn btn-primary btn-whatsapp" title="Falar no WhatsApp">

            FALAR NO WHATSAPP
          </a>
        </div>
      </div>
    </header>
    <div class="mobile-menu-overlay" :class="{ 'is-open': isMenuOpen }" @click="toggleMenu" aria-hidden="true"></div>

    <main class="hero-section">
      <div class="hero-container reveal">
        <div class="hero-text">
          <p class="hero-eyebrow">Edição de alto impacto para quem vive de conteúdo</p>
          <h1 class="hero-title">Dê vida aos seus vídeos</h1>
          <p class="hero-subtitle">
            <span class="highlight">Se preocupe somente em gravar,</span> e deixe a Edição Profissional com a gente!
          </p>
          <ul class="trust-badges" aria-label="Benefícios e diferenciais">

            <li>Estratégia e roteiro focados em conversão</li>
            <li>Motion Graphics e edições cativantes</li>
            <li>Prazo ágil e acompanhamento dedicado</li>
            <li>Pacotes para YouTube, Reels e Ads</li>
          </ul>
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

      <section class="impact-cards reveal" aria-labelledby="impact-stats-title">
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

      <section class="company-logos reveal" aria-labelledby="partners-title">
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

      <section class="services-section reveal" id="services" aria-labelledby="services-title">
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

      <section class="about-us-section reveal" id="about" aria-labelledby="about-title">
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

      <section class="portfolio-section reveal" id="portfolio" aria-labelledby="portfolio-title">
        <div class="portfolio-header">
          <p class="section-tag">/ NOSSO PORTFÓLIO /</p>
          <h2 id="portfolio-title" class="section-title portfolio-title">
            Confira alguns dos projetos de sucesso produzidos pela <span class="highlight">Tower Studio</span>
          </h2>
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

      <section class="testimonials-section reveal" id="testimonials" aria-labelledby="testimonials-title">
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
          :breakpoints="testimonialsSwiperOptions.breakpoints"
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

    <a class="whatsapp-float" href="https://wa.me/5518997762278?text=Quero aumentar meus resultados com vídeos!" target="_blank" rel="noopener" aria-label="Falar no WhatsApp">
      <svg viewBox="0 0 32 32" aria-hidden="true"><path d="M19.11 17.38c-.28-.14-1.64-.81-1.89-.9-.25-.09-.43-.14-.61.14-.18.28-.7.9-.86 1.09-.16.19-.32.21-.6.07-.28-.14-1.17-.43-2.23-1.38-.82-.73-1.37-1.64-1.53-1.92-.16-.28-.02-.43.12-.57.12-.12.28-.32.42-.48.14-.16.18-.28.28-.47.09-.19.05-.35-.02-.5-.07-.14-.61-1.47-.84-2.01-.22-.53-.45-.46-.61-.46-.16 0-.35-.02-.54-.02-.19 0-.5.07-.76.35-.26.28-1 1-1 2.43 0 1.43 1.03 2.81 1.18 3 .14.19 2.03 3.11 4.92 4.37.69.3 1.23.48 1.65.62.69.22 1.33.19 1.82.12.55-.08 1.64-.67 1.87-1.32.23-.65.23-1.21.16-1.32-.07-.11-.25-.18-.53-.32zM16 3C8.83 3 3 8.83 3 16c0 2.3.62 4.47 1.69 6.33L3 29l6.82-1.79C11.6 28.24 13.73 29 16 29c7.18 0 13-5.82 13-13S23.18 3 16 3zM16 26.92c-2.16 0-4.16-.7-5.78-1.89l-.41-.29-4.04 1.06 1.08-3.94-.3-.41C5.38 20.81 4.69 18.88 4.69 16 4.69 9.94 9.94 4.69 16 4.69S27.31 9.94 27.31 16 22.06 27.31 16 26.92z"></path></svg>
    </a>

    <div class="sticky-cta-bar" :class="{ 'is-visible': stickyCtaVisible }" role="region" aria-label="Barra de chamada para ação">
      <span class="text">Pronto para elevar seus vídeos?</span>
      <a href="https://wa.me/5518997762278?text=Quero um orçamento agora!" class="btn btn-primary" target="_blank" rel="noopener">FALAR NO WHATSAPP</a>
    </div>

    <footer class="footer reveal" aria-labelledby="footer-heading">
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
    <a
      href="https://wa.me/5518997762278?text=Olá!%20Quero%20falar%20com%20a%20Tower%20Studio"
      class="whatsapp-float"
      target="_blank"
      rel="noopener noreferrer"
      aria-label="Abrir conversa no WhatsApp"
      title="Falar no WhatsApp"
    >
      <svg width="28" height="28" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false">
        <path d="M27.5 4.5C24.6 1.6 20.6 0 16.3 0 7.3 0 .1 7.2.1 16.1c0 2.8.7 5.4 2 7.8L0 32l8.3-2.2c2.3 1.2 4.9 1.8 7.6 1.8 9 0 16.2-7.2 16.2-16.1 0-4.3-1.7-8.3-4.6-11.2zM16 29.1c-2.4 0-4.7-.6-6.7-1.7l-.5-.3-4.9 1.3 1.3-4.8-.3-.5c-1.2-2.1-1.8-4.5-1.8-6.9C3.1 8.8 9.1 2.9 16.3 2.9c3.5 0 6.7 1.4 9.2 3.8 2.5 2.5 3.9 5.7 3.9 9.2 0 7.2-6 13.2-13.4 13.2zm7.8-9.9c-.4-.2-2.3-1.1-2.6-1.2-.3-.1-.5-.2-.7.2s-.8 1.2-1 1.5c-.2.3-.4.3-.8.1-.4-.2-1.6-.6-3-1.9-1.1-1-1.9-2.2-2.2-2.6-.2-.4 0-.6.2-.8.2-.2.4-.5.6-.7.2-.2.3-.4.4-.6.1-.2 0-.5 0-.7 0-.2-.7-1.8-1-2.5-.3-.7-.5-.6-.7-.6h-.6c-.2 0-.7.1-1.1.5-.4.4-1.5 1.5-1.5 3.6s1.6 4.2 1.8 4.5c.2.3 3.2 4.9 7.8 6.7.9.4 1.6.6 2.2.9.9.3 1.7.3 2.3.2.7-.1 2.3-.9 2.6-1.8.3-.9.3-1.7.2-1.8-.1-.1-.3-.2-.7-.4z" fill="#fff"/>
      </svg>
    </a>
    <div class="sticky-cta-mobile" role="region" aria-label="CTA fixo no mobile">
      <a href="https://wa.me/5518997762278?text=Olá!%20Quero%20um%20orçamento%20rápido" target="_blank" rel="noopener noreferrer" class="btn btn-primary" title="Solicitar orçamento rápido pelo WhatsApp">
        FALAR NO WHATSAPP
      </a>
    </div>
  </div>
</template>

<script>
import { defineComponent, ref, onMounted, onUnmounted, nextTick } from 'vue';
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
    const headerEl = ref(null);

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
      slidesPerView: 1,
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
        992: {
          slidesPerView: 3,
          spaceBetween: 30,
        },
        768: {
          slidesPerView: 1,
          spaceBetween: 30,
        },
        576: {
          slidesPerView: 1,
          spaceBetween: 30,
        },
        0: {
          slidesPerView: 1,
          spaceBetween: 30
        },
      },
    };

    const equalizeTestimonialHeights = () => {
      const cards = document.querySelectorAll('.testimonials-carousel .testimonial-card');
      let maxHeight = 0;
      cards.forEach(card => {
        card.style.height = 'auto';
      });
      cards.forEach(card => {
        const h = card.getBoundingClientRect().height;
        if (h > maxHeight) maxHeight = h;
      });
      cards.forEach(card => {
        card.style.height = `${maxHeight}px`;
      });
    };

    onMounted(async () => {
      await nextTick();
      equalizeTestimonialHeights();
      window.addEventListener('resize', equalizeTestimonialHeights);
      // Header scroll state
      const header = document.querySelector('.header');
      const onScroll = () => {
        if (!header) return;
        if (window.scrollY > 10) header.classList.add('is-scrolled');
        else header.classList.remove('is-scrolled');
      };
      onScroll();
      window.addEventListener('scroll', onScroll, { passive: true });
      // store for cleanup
      headerEl.value = { onScroll };
    });

    onUnmounted(() => {
      window.removeEventListener('resize', equalizeTestimonialHeights);
      if (headerEl.value && headerEl.value.onScroll) {
        window.removeEventListener('scroll', headerEl.value.onScroll);
      }
    });

    return {
      isMenuOpen,
      isHeaderScrolled,
      stickyCtaVisible,
      toggleMenu,
      closeMenu,
      people,
      swiperOptions,
      testimonials,
      testimonialsSwiperOptions,
      equalizeTestimonialHeights,
    };
  },
});
</script>
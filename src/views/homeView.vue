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
              <a v-if="person.link" :href="person.link" target="_blank" rel="noopener noreferrer" class="logo-link">
                <img :src="person.image" :alt="person.alt" class="company-logo" loading="lazy" width="100" height="100" />
              </a>
              <img v-else :src="person.image" :alt="person.alt" class="company-logo" loading="lazy" width="100" height="100" />
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
            Desde crianças, sempre fomos <span class="highlight">apaixonados</span> pelo mundo do audiovisual. O que começou como curiosidade, brincadeira e fascínio por contar histórias através de imagens e sons, se transformou em um propósito de vida. Foi dessa paixão que nasceu a Tower Studios, em 2023, fundada por <span class="highlight">Gabriel Chinchilla e Guilherme Egreja.</span></p>
          <p>
            Desde o início, buscamos mais do que apenas produzir vídeos: queríamos criar <span class="highlight">experiências</span> visuais capazes de emocionar, inspirar e marcar pessoas. Nossa trajetória nos levou a trabalhar com grandes nomes da internet como Super Xandão, Victor Sarro, Gorgonoid, Anna Egreja, Haru, Tinowns, Mais Esports, e Tarcisio Yamamoto muitos outros criadores que marcaram gerações. Também tivemos a honra de atender comércios locais, pequenos criadores e grandes marcas de peso como Vivo, Snickers, Vicsa, entre tantas outras empresas que confiaram no nosso olhar criativo.
          </p>
          <p>
            Em 2025, um novo capítulo se abriu com a chegada de <span class="highlight">Cristiano Zillig</span> como sócio, consolidando uma parceria que ampliou nossa visão e fortaleceu a Tower Studios. Hoje, nosso trabalho vai muito além de simplesmente gravar ou editar. Nós criamos campanhas completas, desenvolvemos conteúdos que conversam diretamente com o público e traduzimos a essência de cada cliente em imagens que se destacam. Seja um vídeo publicitário, um documentário, um videoclipe, uma cobertura de evento ou até mesmo conteúdos para redes sociais, nossa missão é sempre a mesma: transformar ideias em algo que emocione, envolva e gere resultados reais.</p>
          <p>Não importa se você é um microempreendedor querendo mostrar o seu negócio ao mundo, uma marca já consolidada, um criador de conteúdo buscando crescer ou alguém que deseja se destacar nas redes sociais — a Tower Studios é a produtora certa para <span class="highlight">transformar</span> sua visão em <span class="highlight">realidade</span>.</p>
            <p>Acreditamos que o audiovisual é a linguagem que conecta sonhos, pessoas e histórias. E é por isso que dizemos com orgulho: na Tower Studios, cada projeto é mais do que trabalho — é a chance de criar algo inesquecível.</p>
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
            <a v-if="testimonial.link" :href="testimonial.link" target="_blank" rel="noopener noreferrer" class="testimonial-link" :aria-label="'Abrir Instagram de ' + testimonial.name">
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
            </a>
            <article v-else class="testimonial-card">
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
        <a
          href="https://bartechsoftware.com.br/"
          class="footer-credit"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Desenvolvido por Bartech"
          title="Desenvolvido por Bartech"
        >Desenvolvido por Bartech - @https://bartechsoftware.com.br/</a>
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
    const stickyCtaVisible = ref(false);

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
      if (isMenuOpen.value) {
        document.body.classList.add('no-scroll');
      } else {
        document.body.classList.remove('no-scroll');
      }
      updateStickyCta();
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

    const updateStickyCta = () => {
      const threshold = 600;
      const shouldShow = window.scrollY > threshold;
      stickyCtaVisible.value = shouldShow && !isMenuOpen.value;
    };

    const people = [
      { image: new URL('@/assets/super_xandao.png', import.meta.url).href, alt: 'Super Xandão - Parceiro da Tower Studio', name: 'Super Xandão', link: 'https://www.instagram.com/superxandao/' },
      { image: new URL('@/assets/victor_sarro.png', import.meta.url).href, alt: 'Victor Sarro - Cliente da Tower Studio', name: 'Victor Sarro', link: 'https://www.instagram.com/victorsarro/' },
      { image: new URL('@/assets/anna_egreja.jpg', import.meta.url).href, alt: 'Anna Egreja - Colaboradora da Tower Studio', name: 'Anna Egreja', link: 'https://www.instagram.com/annaegreja/' },
      { image: new URL('@/assets/gorgonoide.jpg', import.meta.url).href, alt: 'Gorgonoid - Parceiro de conteúdo digital', name: 'Gorgonoid', link: 'https://www.instagram.com/gorgonoid/' },
      { image: new URL('@/assets/tinows.jpg', import.meta.url).href, alt: 'Tinowns - Profissional de eSports', name: 'Tinowns', link: 'https://www.instagram.com/thiagotinowns/' },
      { image: new URL('@/assets/ericat.jpg', import.meta.url).href, alt: 'Ericat - Streamer e Influencer', name: 'Ericat', link: 'https://www.instagram.com/ericat_lol/' },
      { image: new URL('@/assets/gabriel_curiosidades.png', import.meta.url).href, alt: 'Gabriel Chinchilla - Criador de Conteúdo', name: 'Gabriel Chinchilla', link: 'https://www.instagram.com/ga_chinchilla/' },
      { image: new URL('@/assets/snickers.png', import.meta.url).href, alt: 'Snickers - Marca parceira', name: 'Snickers', link: 'https://www.instagram.com/snickersbr/' },
      { image: new URL('@/assets/vivo_cliente.jpg', import.meta.url).href, alt: 'Vivo - Empresa de Telecomunicações', name: 'Vivo', link: 'https://www.instagram.com/vivo/' },
      // Novos parceiros com placeholder de imagem
      { image: new URL('@/assets/brazuca_logo.png', import.meta.url).href, alt: 'Brazuca Filmes - Parceiro da Tower Studio', name: 'Brazuca Filmes', link: 'https://www.instagram.com/brazucafilmes/' },
      { image: new URL('@/assets/analu.png', import.meta.url).href, alt: 'Analu - Parceira da Tower Studio', name: 'Analu', link: 'https://www.instagram.com/analuproductdaily/' },
      { image: new URL('@/assets/haru.webp', import.meta.url).href, alt: 'Haru - Parceiro da Tower Studio', name: 'Haru', link: 'https://www.instagram.com/haru_jiggly/' },
      { image: new URL('@/assets/maissports.jpg', import.meta.url).href, alt: 'Mais esports - Parceiro da Tower Studio', name: 'Mais esports', link: 'https://www.instagram.com/maisesportsbr/' },
      { image: new URL('@/assets/yamanerd.jpg', import.meta.url).href, alt: 'Tarcisio Yamamoto - Parceiro da Tower Studio', name: 'Tarcisio Yamamoto', link: 'https://www.instagram.com/tar.yamamoto/' },
    ];

    const testimonials = [
      {
        name: "Brazuca Filmes",
        role: "Produtora Audiovisual",
        avatar: new URL('@/assets/brazuca_logo.png', import.meta.url).href,
        text: "A Tower é uma parceira essencial para a Brazuca Filmes. Eles são rápidos, proativos e dinâmicos, sempre entregando um excelente custo-benefício. O que mais admiro é a disposição de ouvir, aprender e entender até as demandas mais complexas, garantindo a melhor execução possível. Ao longo de nossa parceria, nunca nos deixaram na mão — pelo contrário, sempre surpreenderam pela qualidade e agilidade. A Tower tem nossa total confiança, pois conseguem editar qualquer filme com excelência.",
        rating: 5,
        link: 'https://www.instagram.com/brazucafilmes/'
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
      window.addEventListener('resize', updateStickyCta);
      // Header scroll state
      const header = document.querySelector('.header');
      const onScroll = () => {
        if (!header) return;
        if (window.scrollY > 10) header.classList.add('is-scrolled');
        else header.classList.remove('is-scrolled');
        updateStickyCta();
      };
      onScroll();
      window.addEventListener('scroll', onScroll, { passive: true });
      // store for cleanup
      headerEl.value = { onScroll };
    });

    onUnmounted(() => {
      window.removeEventListener('resize', equalizeTestimonialHeights);
      window.removeEventListener('resize', updateStickyCta);
      if (headerEl.value && headerEl.value.onScroll) {
        window.removeEventListener('scroll', headerEl.value.onScroll);
      }
    });

    return {
      isMenuOpen,
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
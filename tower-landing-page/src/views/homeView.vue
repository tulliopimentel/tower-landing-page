<template>
  <div class="landing-page">
    <header class="header">
      <div class="container">
        <div class="logo">
          <img src="data:image/png;base64,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" alt="Logo da Empresa de Edição de Vídeo" />
        </div>
        <nav class="main-nav">
          <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#services">Serviços</a></li>
            <li><a href="#about">Quem somos nós</a></li>
            <li><a href="#portfolio">Portfólio</a></li>
            <li><a href="#testimonials">Depoimentos</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <main class="hero-section">
      <div class="container">
        <h1 class="hero-title">Dê vida aos seus vídeos</h1>
        <p class="hero-subtitle">Chega de se preocupar com edições, se preocupe somente em gravar e deixe o resto com a gente.</p>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
};
</script>

<style scoped>
.landing-page {
  font-family: Arial, sans-serif;
  color: #333;
}

.header {
  background-color: #333; /* Fundo do menu: preto mais claro */
  padding: 15px 0;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.header .container {
  display: flex;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  justify-content: flex-start;
  position: relative;
}

.logo {
  flex-shrink: 0;
  margin-right: auto;
}

.logo img {
  height: 40px;
  max-width: 100%;
}

.main-nav {
  flex-grow: 1;
  display: flex;
  justify-content: center;
}

.main-nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  gap: 30px;
}

.main-nav li a {
  text-decoration: none;
  color: #f0f0f0; /* Cor do texto do menu: branco quase puro para contraste */
  font-weight: bold;
  font-size: 16px;
  transition: color 0.3s ease;
}

.main-nav li a:hover {
  color: #ff6666; /* Vermelho claro */
}

.hero-section {
  text-align: center;
  padding: 100px 20px;
  background-color: #333; /* Fundo da seção hero: preto mais claro (mesma cor do menu) */
  color: #f0f0f0; /* Cor do texto na seção hero: branco quase puro para contraste */
}

.hero-section .container {
  max-width: 800px;
  margin: 0 auto;
}

.hero-title {
  font-size: 4em;
  margin-bottom: 20px;
  color: #f0f0f0; /* Título também branco quase puro */
  line-height: 1.2;
}

.hero-subtitle {
  font-size: 1.5em;
  color: #ddd; /* Um cinza mais claro para o subtítulo */
  line-height: 1.5;
}

@media (max-width: 768px) {
  .header .container {
    flex-direction: column;
    gap: 15px;
    justify-content: center;
  }

  .logo {
    margin-right: 0;
  }

  .main-nav {
    width: 100%;
  }

  .main-nav ul {
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px;
  }

  .hero-title {
    font-size: 2.5em;
  }

  .hero-subtitle {
    font-size: 1.2em;
  }
}
</style>
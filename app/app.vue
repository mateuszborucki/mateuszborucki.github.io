<template>
  <div class="page">
    <header class="hero">
      <div class="hero-bg" :style="{ backgroundImage: `url(${heroImage})` }" />
      <div class="hero-overlay" />
      <div class="hero-inner">
        <h1 class="hero-title">IZO-MAX</h1>
        <p class="hero-subtitle">Artur Piórkowski</p>
      </div>
    </header>

    <main class="main">
      <section class="contact">
        <a href="tel:+48606839494" class="contact-link">📞 606 839 494</a>
        <a href="mailto:izo-max@wp.pl" class="contact-link">✉️ izo-max@wp.pl</a>
      </section>

      <section class="section">
        <p class="lead">
          Specjalizuję się w kompleksowej realizacji izolacji przemysłowych – od precyzyjnych pomiarów, przez wykonawstwo warsztatowe, aż po profesjonalny montaż u klienta.
        </p>
        <p>
          Gwarantuję solidność wykonania, dokładność pomiarów oraz terminowość realizacji.
        </p>
      </section>

      <div class="categories-row">
        <section v-for="cat in categories" :key="cat.title" class="category">
          <h2 class="category-title">{{ cat.title }}</h2>
          <div class="category-body">
            <div class="category-text">
              <p v-if="cat.lead" class="category-lead">{{ cat.lead }}</p>
              <ul v-if="cat.items" class="list">
                <li v-for="(item, i) in cat.items" :key="i">{{ item }}</li>
              </ul>
              <p v-if="cat.para" class="category-para">{{ cat.para }}</p>
            </div>
            <div v-if="cat.images?.length" class="category-gallery">
              <img
                v-for="(img, i) in cat.images"
                :key="i"
                :src="img.src"
                :alt="cat.title + ' – zdjęcie ' + (i + 1)"
                class="category-img"
                loading="lazy"
              />
            </div>
          </div>
        </section>
      </div>
      <footer class="footer">
        <p>Artur Piórkowski</p>
      </footer>
    </main>
  </div>
</template>

<script setup lang="ts">
const heroImage = '/galeria/zbiorniki/20190429_171305.jpg'

const categories = [
  {
    title: 'Wykonuję',
    lead: 'Izolacje termiczne, ciepłochronne i zimnochronne dla:',
    items: ['rurociągów', 'zbiorników', 'kanałów wentylacyjnych'],
    images: [
      { src: '/galeria/zbiorniki/20190429_171305.jpg' },
      { src: '/galeria/zbiorniki/img20251011163338.jpg' },
      { src: '/galeria/zbiorniki/img20251011163359.jpg' }
    ]
  },
  {
    title: 'Produkcja wkładów kominowych',
    items: ['owalnych', 'okrągłych', 'dwupłaszczowych'],
    images: [
      { src: '/galeria/wklady_kominowe/img20240924181545.jpg' },
      { src: '/galeria/wklady_kominowe/img20250920164611.jpg' },
      { src: '/galeria/okrągłe/img20250816141952.jpg' },
      { src: '/galeria/okrągłe/img20250816142043.jpg' }
    ]
  },
  {
    title: 'Produkcja elementów wentylacyjnych',
    para: 'Zajmuję się produkcją elementów wentylacyjnych oraz realizacją nietypowych kształtek i elementów specjalnych („dziwolągów”) z blachy, wykonywanych na indywidualne zamówienie klienta.',
    images: [
      { src: '/galeria/elementy_wentylacja/20170809_074340.jpg' },
      { src: '/galeria/elementy_wentylacja/img20250421091117.jpg' },
      { src: '/galeria/elementy_wentylacja/zdjecie0332.jpg' }
    ]
  }
]

useHead({
  title: 'IZO-MAX – Artur Piórkowski | Izolacje przemysłowe',
  meta: [
    { name: 'description', content: 'Izolacje przemysłowe, wkłady kominowe, elementy wentylacyjne. Rurociągi, zbiorniki, kanały. Tel. 606 839 494.' }
  ]
})
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif;
  font-size: 18px;
  line-height: 1.6;
  color: #1a1a1a;
  background: #f5f5f0;
}

body {
  margin: 0;
}

.page {
  min-height: 100vh;
}

.hero {
  position: relative;
  width: 100%;
  min-height: 42vh;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: -20px;
  background-size: cover;
  background-position: center;
  filter: blur(8px);
  transform: scale(1.05);
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.35);
}

.hero-inner {
  position: relative;
  z-index: 1;
  text-align: center;
  padding: 2rem 1rem;
}

.hero-title {
  font-size: clamp(2rem, 6vw, 3.5rem);
  font-weight: 700;
  letter-spacing: 0.08em;
  margin: 0;
  color: #fff;
  text-shadow: 0 2px 12px rgba(0, 0, 0, 0.4);
}

.hero-subtitle {
  font-size: clamp(1rem, 2.5vw, 1.35rem);
  margin: 0.5rem 0 0;
  color: rgba(255, 255, 255, 0.95);
  text-shadow: 0 1px 6px rgba(0, 0, 0, 0.3);
}

.main {
  max-width: 56rem;
  margin: 0 auto;
  padding: 2.5rem 1.5rem 4rem;
}

.contact {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
  margin-bottom: 2.5rem;
}

.contact-link {
  color: #1a1a1a;
  text-decoration: none;
  font-weight: 500;
  padding: 0.5rem 1rem;
  background: #e8e4d8;
  border-radius: 6px;
  transition: background 0.2s;
}

.contact-link:hover {
  background: #ddd9cc;
}

.section {
  margin-bottom: 2rem;
}

.section h2 {
  font-size: 1.2rem;
  font-weight: 600;
  margin: 0 0 0.75rem;
  color: #2c2c2c;
}

.lead {
  font-size: 1.05rem;
  margin: 0;
  color: #333;
}

.list {
  margin: 0.5rem 0 0;
  padding-left: 1.5rem;
}

.list li {
  margin-bottom: 0.25rem;
}

.categories-row {
  display: grid;
  grid-template-columns: 1fr;
  margin-bottom: 2rem;
}

@media (min-width: 768px) {
  .categories-row {
    grid-template-columns: repeat(3, 1fr);
    gap: 0;
  }
}

.category {
  margin-bottom: 0;
  min-width: 0;
}

.categories-row .category:nth-child(1) {
  background: #e8e4d8;
  padding: 1.25rem;
}

.categories-row .category:nth-child(2) {
  background: #dde5e0;
  padding: 1.25rem;
}

.categories-row .category:nth-child(3) {
  background: #e2e4eb;
  padding: 1.25rem;
}

.category-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin: 0 0 1rem;
  color: #2c2c2c;
}

.category-body {
  display: grid;
  gap: 1.25rem;
}

@media (min-width: 640px) and (max-width: 767px) {
  .category-body {
    grid-template-columns: 1fr 1fr;
    align-items: start;
  }

  .category-body:has(.category-gallery) .category-text {
    min-width: 0;
  }
}

@media (min-width: 768px) {
  .categories-row .category-body {
    grid-template-columns: 1fr;
  }
}

.category-lead,
.category-para {
  margin: 0 0 0.5rem;
  color: #333;
}

.category-para {
  margin-bottom: 0;
}

.category-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
  gap: 0.5rem;
}

.category-img {
  width: 100%;
  aspect-ratio: 4/3;
  object-fit: cover;
  border-radius: 8px;
  background: #e8e4d8;
}

.guarantee {
  padding: 1.25rem;
  background: #e8e4d8;
  border-radius: 8px;
  border-left: 4px solid #c9a227;
}

.guarantee p {
  margin: 0;
  font-weight: 500;
}

.footer {
  text-align: center;
  margin-top: 3rem;
  padding-top: 2rem;
  border-top: 1px solid #ddd;
  color: #666;
  font-size: 0.95rem;
}

.footer p {
  margin: 0;
}
</style>

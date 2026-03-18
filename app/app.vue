<template>
  <div class="page">
    <header class="header">
      <h1 class="title">IZO-MAX</h1>
      <p class="subtitle">Artur Piórkowski</p>
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
      </section>

      <section class="section">
        <h2>Wykonuję</h2>
        <ul class="list">
          <li>izolacje termiczne,</li>
          <li>izolacje ciepłochronne,</li>
          <li>izolacje zimnochronne</li>
        </ul>
        <p class="for">dla:</p>
        <ul class="list">
          <li>rurociągów,</li>
          <li>zbiorników,</li>
          <li>kanałów wentylacyjnych.</li>
        </ul>
      </section>

      <section class="section">
        <h2>🔧 Produkcja wkładów kominowych</h2>
        <ul class="list">
          <li>owalnych,</li>
          <li>okrągłych,</li>
          <li>dwupłaszczowych.</li>
        </ul>
      </section>

      <section class="section">
        <h2>🏭 Produkcja elementów wentylacyjnych</h2>
        <p>
          Zajmuję się również produkcją elementów wentylacyjnych oraz realizacją nietypowych kształtek i elementów specjalnych („dziwolągów”) z blachy, wykonywanych na indywidualne zamówienie klienta.
        </p>
      </section>

      <section class="section gallery-section">
        <h2>Galeria realizacji</h2>
        <div v-for="group in gallery" :key="group.title" class="gallery-group">
          <h3 class="gallery-group-title">{{ group.title }}</h3>
          <div class="gallery-grid">
            <img
              v-for="(img, i) in group.images"
              :key="i"
              :src="img.src"
              :alt="group.title + ' – zdjęcie ' + (i + 1)"
              class="gallery-img"
              loading="lazy"
            />
          </div>
        </div>
      </section>

      <section class="section guarantee">
        <p>
          Gwarantuję solidność wykonania, dokładność pomiarów oraz terminowość realizacji.
        </p>
      </section>

      <footer class="footer">
        <p>Artur Piórkowski</p>
      </footer>
    </main>
  </div>
</template>

<script setup lang="ts">
const gallery = [
  {
    title: 'Elementy wentylacyjne',
    images: [
      { src: '/galeria/elementy_wentylacja/20170809_074340.jpg' },
      { src: '/galeria/elementy_wentylacja/img20250421091117.jpg' },
      { src: '/galeria/elementy_wentylacja/zdjecie0332.jpg' }
    ]
  },
  {
    title: 'Wkłady kominowe okrągłe',
    images: [
      { src: '/galeria/okrągłe/img20250816141937.jpg' },
      { src: '/galeria/okrągłe/img20250816141945.jpg' },
      { src: '/galeria/okrągłe/img20250816141952.jpg' },
      { src: '/galeria/okrągłe/img20250816142043.jpg' }
    ]
  },
  {
    title: 'Wkłady kominowe',
    images: [
      { src: '/galeria/wklady_kominowe/img20240924181545.jpg' },
      { src: '/galeria/wklady_kominowe/img20250920164611.jpg' },
      { src: '/galeria/wklady_kominowe/img20250920164715.jpg' },
      { src: '/galeria/wklady_kominowe/img20250920171948.jpg' },
      { src: '/galeria/wklady_kominowe/img20260203224952.jpg' }
    ]
  },
  {
    title: 'Zbiorniki',
    images: [
      { src: '/galeria/zbiorniki/20190429_171305.jpg' },
      { src: '/galeria/zbiorniki/img20251011163338.jpg' },
      { src: '/galeria/zbiorniki/img20251011163359.jpg' },
      { src: '/galeria/zbiorniki/20190429_171305%20%E2%80%94%20kopia.jpg' }
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

.page {
  max-width: 42rem;
  margin: 0 auto;
  padding: 2rem 1.5rem 4rem;
}

.header {
  text-align: center;
  margin-bottom: 2.5rem;
  padding-bottom: 2rem;
  border-bottom: 2px solid #c9a227;
}

.title {
  font-size: 2rem;
  font-weight: 700;
  letter-spacing: 0.05em;
  margin: 0;
  color: #1a1a1a;
}

.subtitle {
  font-size: 1.1rem;
  margin: 0.5rem 0 0;
  color: #444;
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
  margin: 0.5rem 0 1rem;
  padding-left: 1.5rem;
}

.list li {
  margin-bottom: 0.25rem;
}

.for {
  margin: 0.75rem 0 0.25rem;
  font-weight: 500;
}

.gallery-section {
  max-width: 100%;
}

.gallery-group {
  margin-bottom: 2.5rem;
}

.gallery-group:last-child {
  margin-bottom: 0;
}

.gallery-group-title {
  font-size: 1.1rem;
  font-weight: 600;
  margin: 0 0 1rem;
  color: #2c2c2c;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 0.75rem;
}

.gallery-img {
  width: 100%;
  aspect-ratio: 4/3;
  object-fit: cover;
  border-radius: 6px;
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

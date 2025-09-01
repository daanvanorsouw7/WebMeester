<template>
  <div class="website-container">
    <header class="main-header">
      <div class="header-content">
        <h1 class="header-title">WebMeesters</h1>
        <nav :class="{ 'nav-menu': true, 'is-active': isMobileMenuOpen }">
          <a class="nav-link" :class="{ 'active-link': activeSection === 'introductie' }" @click="scrollToSection('introductie')">Introductie</a>
          <a class="nav-link" :class="{ 'active-link': activeSection === 'diensten' }" @click="scrollToSection('diensten')">Diensten</a>
          <a class="nav-link" :class="{ 'active-link': activeSection === 'tarieven' }" @click="scrollToSection('tarieven')">Tarieven</a>
          <a class="nav-link" :class="{ 'active-link': activeSection === 'projecten' }" @click="scrollToSection('projecten')">Projecten</a>
          <a class="nav-link" :class="{ 'active-link': activeSection === 'contact' }" @click="scrollToSection('contact')">Contact</a>
        </nav>
        <button class="menu-toggle" @click="toggleMobileMenu">
          <div class="menu-icon"></div>
          <div class="menu-icon"></div>
          <div class="menu-icon"></div>
        </button>
      </div>
    </header>

    <main class="main-content">
      <section id="introductie" class="hero-section fade-in">
        <div class="hero-content">
          <div class="hero-text-container">
            <h2 class="hero-title">Op maat gemaakte websites die indruk achterlaten.</h2>
            <p class="hero-description">Wij ontwikkelen en verbeteren websites die niet alleen mooi ogen, maar ook volledig zijn afgestemd op jouw merk. Zo zorgen we dat bezoekers geboeid raken en eenvoudig tot actie overgaan.</p>
            <div class="hero-buttons">
              <a class="button primary-button" @click="scrollToSection('diensten')">Ontdek onze diensten</a>
              <a class="button secondary-button" @click="scrollToSection('projecten')">Bekijk onze projecten</a>
            </div>
          </div>
          <div class="hero-image-container">
            <img src="./assets/design.png" alt="Creative design" class="hero-image" />
          </div>
        </div>
      </section>

      <section id="diensten" class="services-section fade-in">
        <div class="section-title">
          <h2>Onze Diensten</h2>
        </div>
        <div class="services-grid">
          <div class="service-card">
            <img src="./assets/CustomWebDesign.png" alt="Web Design Icon" class="service-icon" />
            <h3 class="service-card-title">Custom Web Design</h3>
            <p class="service-card-text">
              We ontwerpen moderne, responsieve websites die volledig zijn afgestemd op jouw merkidentiteit en zakelijke doelstellingen. Van wireframes tot de laatste pixel, elk detail wordt zorgvuldig vormgegeven om een unieke en functionele ervaring te bieden.
            </p>
          </div>
          <div class="service-card">
            <img src="./assets/ResponsieveDesign.png" alt="Responsive Design Icon" class="service-icon" />
            <h3 class="service-card-title">Responsieve Design</h3>
            <p class="service-card-text">
              Zorg ervoor dat jouw website er altijd perfect uitziet, ongeacht het apparaat. Onze ontwerpen passen zich naadloos aan voor desktop, tablet en mobiel, zodat jouw gebruikers altijd een optimale en consistente ervaring hebben.
            </p>
          </div>
          <div class="service-card">
            <img src="./assets/SnelheidOptimalisatie.png" alt="Speed Optimization Icon" class="service-icon" />
            <h3 class="service-card-title">Snelheid Optimalisatie</h3>
            <p class="service-card-text">
              Snelle websites zijn essentieel voor zowel gebruiksvriendelijkheid als SEO. Wij optimaliseren de laadtijden en performance van je website, wat resulteert in een betere ranking en een vloeiende ervaring voor je bezoekers.
            </p>
          </div>
          <div class="service-card">
            <img src="./assets/SEO-Optimalisatie.png" alt="SEO Optimalisatie" class="service-icon" />
            <h3 class="service-card-title">SEO Optimalisatie</h3>
            <p class="service-card-text">
              Verhoog je online zichtbaarheid en trek meer organisch verkeer aan. We voeren zowel technische als content-optimalisatie uit om ervoor te zorgen dat jouw website hoog scoort in zoekmachines zoals Google.
            </p>
          </div>
          <div class="service-card service-card-full">
            <img src="./assets/Onderhoud.png" alt="Onderhoud Icon" class="service-icon" />
            <h3 class="service-card-title">Onderhoud</h3>
            <p class="service-card-text">
              Een website is nooit 'af'. Wij bieden doorlopend onderhoud en updates om ervoor te zorgen dat je website altijd veilig, actueel en snel blijft. Zo kun jij je richten op je bedrijf, terwijl wij de technische zaken regelen.
            </p>
          </div>
        </div>
      </section>

      <section id="tarieven" class="pricing-section fade-in">
        <div class="section-title">
          <h2>Tarieven</h2>
        </div>
        <div class="pricing-grid">
          <div class="pricing-card">
            <h3 class="pricing-title">Starter</h3>
            <p class="pricing-price">€399</p>
            <ul class="pricing-features">
              <li>Responsive Design</li>
              <li>SEO-optimalisatie (basis)</li>
              <li>Snelheid-optimalisatie</li>
              <li>Contactformulier</li>
              <li class="disabled">Geen Onderhoud</li>
            </ul>
            <a class="button primary-button" @click="selectPackageAndScroll('Starter')">Kies Pakket</a>
          </div>
          <div class="pricing-card featured">
            <h3 class="pricing-title">Professional</h3>
            <p class="pricing-price">€599</p>
            <ul class="pricing-features">
              <li>Alles in Starter pakket</li>
              <li>Aangepast webdesign</li>
              <li>Uitgebreide SEO-optimalisatie</li>
              <li>Analytics-integratie</li>
              <li>Inclusief 6 maanden Onderhoud</li>
            </ul>
            <a class="button primary-button" @click="selectPackageAndScroll('Professional')">Kies Pakket</a>
          </div>
          <div class="pricing-card">
            <h3 class="pricing-title">Enterprise</h3>
            <p class="pricing-price">Offerte op aanvraag</p>
            <ul class="pricing-features">
              <li>Alles in Professional pakket</li>
              <li>Aangepaste functies</li>
              <li>Onbeperkte revisies</li>
              <li>Geavanceerde beveiliging</li>
              <li>Doorlopend onderhoud</li>
            </ul>
            <a class="button primary-button" @click="selectPackageAndScroll('Enterprise')">Kies Pakket</a>
          </div>
        </div>
      </section>

      <section id="projecten" class="projects-section fade-in">
        <div class="section-title">
          <h2>Onze Projecten</h2>
        </div>
        <div class="projects-carousel-container">
          <button class="carousel-nav prev" @click="prevSlide">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
              <path fill-rule="evenodd" d="M7.72 12.53a.75.75 0 0 1 0-1.06l7.5-7.5a.75.75 0 1 1 1.06 1.06L9.31 12l6.97 6.97a.75.75 0 1 1-1.06 1.06l-7.5-7.5Z" clip-rule="evenodd" />
            </svg>
          </button>
          <div class="projects-carousel-track" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
            <div v-for="(project, index) in projects" :key="index" class="project-slide">
              <img :src="project.image" :alt="project.title" class="project-image" />
              <div class="project-info">
                <h3>{{ project.title }}</h3>
                <p>{{ project.description }}</p>
                <a :href="project.link" target="_blank" class="button primary-button small-button">Bekijk Project</a>
              </div>
            </div>
          </div>
          <button class="carousel-nav next" @click="nextSlide">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
              <path fill-rule="evenodd" d="M16.28 11.47a.75.75 0 0 1 0 1.06l-7.5 7.5a.75.75 0 0 1-1.06-1.06L14.69 12 7.72 5.03a.75.75 0 0 1 1.06-1.06l7.5 7.5Z" clip-rule="evenodd" />
            </svg>
          </button>
        </div>
      </section>

      <section id="contact" class="contact-section fade-in">
        <div class="section-title">
          <h2>Contact</h2>
        </div>
        <form @submit.prevent="submitForm" class="contact-form">
          <div class="form-row">
            <div class="form-group">
              <label for="firstName">Voornaam</label>
              <input type="text" id="firstName" v-model="form.firstName" required />
            </div>
            <div class="form-group">
              <label for="lastName">Achternaam</label>
              <input type="text" id="lastName" v-model="form.lastName" required />
            </div>
          </div>
          <div class="form-group">
            <label for="email">E-mailadres</label>
            <input type="email" id="email" v-model="form.email" required />
          </div>
          <div class="form-group">
            <label for="phone">Telefoonnummer</label>
            <input type="tel" id="phone" v-model="form.phone" />
          </div>
          <div class="form-group">
            <label for="interest">Pakket</label>
            <select id="interest" v-model="form.interest">
              <option value="">Kies een optie</option>
              <option value="Starter">Starter</option>
              <option value="Professional">Professional</option>
              <option value="Enterprise">Enterprise</option>
            </select>
          </div>
          <div class="form-group">
            <label for="message">Speciale vereisten</label>
            <textarea id="message" v-model="form.message" required></textarea>
          </div>
          <button type="submit" class="submit-button">Gratis een offerte aanvragen</button>
        </form>
      </section>
    </main>

    <footer class="main-footer">
      <p class="copyright">&copy; 2025 WebMeesters. Alle rechten voorbehouden.</p>
      <div class="footer-links">
        <a class="nav-link" @click="scrollToSection('introductie')">Introductie</a>
        <a class="nav-link" @click="scrollToSection('diensten')">Diensten</a>
        <a class="nav-link" @click="scrollToSection('tarieven')">Tarieven</a>
        <a class="nav-link" @click="scrollToSection('projecten')">Projecten</a>
        <a class="nav-link" @click="scrollToSection('contact')">Contact</a>
      </div>
    </footer>
  </div>
</template>

<script lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import GearProfitsImage from './assets/GearProfits.png';
import DaanVanOrsouwImage from './assets/daanvanorsouw.png';

export default {
  name: 'App',
  setup() {
    const isMobileMenuOpen = ref(false);
    const currentSlide = ref(0);
    const projects = ref([
      { id: 1, title: 'GearProfits', description: 'Deze webshop toont producten via Amazon Affiliate-links en biedt een gebruiksvriendelijke ervaring die passief inkomen mogelijk maakt.', image: GearProfitsImage, link: 'https://gearprofits.daanvanorsouw.nl/' },
      { id: 2, title: 'Portfolio Daan Van Orsouw', description: 'De portfolio van daanvanorsouw.nl toont projecten in webontwikkeling en software, overzichtelijk en professioneel gepresenteerd.', image: DaanVanOrsouwImage, link: 'https://daanvanorsouw.nl' },
    ]);
    let carouselInterval: number | null = null;
    let observer: IntersectionObserver | null = null;
    const activeSection = ref('introductie');

    const form = ref({
      firstName: '',
      lastName: '',
      email: '',
      phone: '',
      interest: '',
      message: ''
    });

    const toggleMobileMenu = () => {
      isMobileMenuOpen.value = !isMobileMenuOpen.value;
    };

    const scrollToSection = (sectionId: string) => {
      const element = document.getElementById(sectionId);
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
        isMobileMenuOpen.value = false;
      }
    };

    const selectPackageAndScroll = (packageName: string) => {
      form.value.interest = packageName;
      scrollToSection('contact');
    };

    const nextSlide = () => {
      currentSlide.value = (currentSlide.value + 1) % projects.value.length;
    };

    const prevSlide = () => {
      currentSlide.value = (currentSlide.value - 1 + projects.value.length) % projects.value.length;
    };

    const startCarouselAutoPlay = () => {
      if (carouselInterval) clearInterval(carouselInterval);
      carouselInterval = setInterval(nextSlide, 5000) as unknown as number;
    };

    const setupIntersectionObserver = () => {
      const sections = document.querySelectorAll('section');
      const options = {
        root: null,
        rootMargin: '0px',
        threshold: 0.3
      };

      observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            activeSection.value = entry.target.id;
            entry.target.classList.add('visible');
          } else {
            entry.target.classList.remove('visible');
          }
        });
      }, options);

      sections.forEach(section => {
        observer?.observe(section);
      });
    };

    const submitForm = () => {
      console.log('Form submitted:', form.value);
      alert('Je hebt het formulier verzonden! Dit is een portfolio project en niet echt in gebruik.');
      form.value = { firstName: '', lastName: '', email: '', phone: '', interest: '', message: '' };
    };

    onMounted(() => {
      setupIntersectionObserver();
      startCarouselAutoPlay();
    });

    onUnmounted(() => {
      if (carouselInterval) {
        clearInterval(carouselInterval);
      }
      if (observer) {
        observer.disconnect();
      }
    });

    return {
      isMobileMenuOpen,
      scrollToSection,
      toggleMobileMenu,
      form,
      submitForm,
      projects,
      currentSlide,
      nextSlide,
      prevSlide,
      activeSection,
      selectPackageAndScroll,
    };
  }
};
</script>
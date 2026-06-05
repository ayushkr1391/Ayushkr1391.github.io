<script lang="ts">
  import Navbar from './lib/components/Navbar.svelte';
  import ScrollProgress from './lib/components/ScrollProgress.svelte';
  import BackToTop from './lib/components/BackToTop.svelte';
  import ParticleBackground from './lib/components/ParticleBackground.svelte';
  import Hero from './lib/sections/Hero.svelte';
  import About from './lib/sections/About.svelte';
  import Skills from './lib/sections/Skills.svelte';
  import Projects from './lib/sections/Projects.svelte';
  import Timeline from './lib/sections/Timeline.svelte';
  import GitHub from './lib/sections/GitHub.svelte';
  import FunFacts from './lib/sections/FunFacts.svelte';
  import Contact from './lib/sections/Contact.svelte';
  import Footer from './lib/sections/Footer.svelte';
</script>

<ParticleBackground />
<ScrollProgress />
<Navbar />

<main>
  <Hero />
  <About />
  <Skills />
  <Projects />
  <Timeline />
  <GitHub />
  <FunFacts />
  <Contact />
  <Footer />
</main>

<BackToTop />

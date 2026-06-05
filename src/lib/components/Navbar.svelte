<script lang="ts">
  import { onMount } from 'svelte';
  
  let scrollY = $state(0);
  let activeSection = $state('home');
  
  const navItems = [
    { id: 'home', label: 'Home' },
    { id: 'about', label: 'About' },
    { id: 'skills', label: 'Skills' },
    { id: 'projects', label: 'Projects' },
    { id: 'timeline', label: 'Journey' },
    { id: 'contact', label: 'Contact' }
  ];
  
  let mobileMenuOpen = $state(false);
  
  onMount(() => {
    const handleScroll = () => {
      scrollY = window.scrollY;
      
      for (const item of navItems) {
        const section = document.getElementById(item.id);
        if (section) {
          const rect = section.getBoundingClientRect();
          if (rect.top <= 100 && rect.bottom >= 100) {
            activeSection = item.id;
            break;
          }
        }
      }
    };
    
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
  
  function scrollTo(id: string) {
    const el = document.getElementById(id);
    if (el) {
      el.scrollIntoView({ behavior: 'smooth' });
      mobileMenuOpen = false;
    }
  }
</script>

<nav class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 {scrollY > 50 ? 'glass py-3' : 'py-5'}">
  <div class="max-w-6xl mx-auto px-4 flex items-center justify-between">
    <button onclick={() => scrollTo('home')} class="text-xl font-bold gradient-text">
      AK
    </button>
    
    <div class="hidden md:flex items-center gap-8">
      {#each navItems as item}
        <button 
          onclick={() => scrollTo(item.id)}
          class="text-sm font-medium transition-colors {activeSection === item.id ? 'text-primary' : 'text-muted hover:text-foreground'}"
        >
          {item.label}
        </button>
      {/each}
    </div>
    
    <button 
      onclick={() => mobileMenuOpen = !mobileMenuOpen}
      class="md:hidden p-2 text-foreground"
      aria-label="Toggle menu"
    >
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        {#if mobileMenuOpen}
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        {:else}
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        {/if}
      </svg>
    </button>
  </div>
  
  {#if mobileMenuOpen}
    <div class="md:hidden glass mt-2 mx-4 p-4 rounded-xl">
      {#each navItems as item}
        <button 
          onclick={() => scrollTo(item.id)}
          class="block w-full text-left py-3 px-4 text-sm font-medium transition-colors rounded-lg {activeSection === item.id ? 'text-primary bg-primary/10' : 'text-muted hover:text-foreground hover:bg-white/5'}"
        >
          {item.label}
        </button>
      {/each}
    </div>
  {/if}
</nav>

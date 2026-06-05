<script lang="ts">
  import { onMount } from 'svelte';
  
  const roles = ['Student', 'Unity Developer', 'Learner'];
  let currentRole = $state(0);
  let displayText = $state('');
  let isDeleting = $state(false);
  
  onMount(() => {
    let timeout: ReturnType<typeof setTimeout>;
    
    function type() {
      const fullText = roles[currentRole];
      
      if (!isDeleting) {
        displayText = fullText.substring(0, displayText.length + 1);
        if (displayText === fullText) {
          timeout = setTimeout(() => { isDeleting = true; type(); }, 2000);
          return;
        }
      } else {
        displayText = fullText.substring(0, displayText.length - 1);
        if (displayText === '') {
          isDeleting = false;
          currentRole = (currentRole + 1) % roles.length;
        }
      }
      
      timeout = setTimeout(type, isDeleting ? 50 : 100);
    }
    
    type();
    return () => clearTimeout(timeout);
  });
  
  const floatingCards = [
    { label: 'Student', icon: '📚', delay: '0s' },
    { label: 'Unity Dev', icon: '🎮', delay: '2s' },
    { label: 'Learner', icon: '💡', delay: '4s' }
  ];
</script>

<section id="home" class="relative min-h-screen flex items-center justify-center px-4 pt-20">
  <div class="absolute inset-0 overflow-hidden">
    <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-primary/20 rounded-full blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-1/4 right-1/4 w-96 h-96 bg-accent/20 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 2s;"></div>
  </div>
  
  <div class="relative z-10 text-center max-w-4xl mx-auto">
    <div class="mb-6">
      <span class="inline-block px-4 py-2 glass text-sm font-medium text-primary">
        Welcome to my portfolio
      </span>
    </div>
    
    <h1 class="text-4xl sm:text-5xl md:text-7xl font-bold mb-6">
      {"Hi, I'm "}
      <span class="gradient-text">Ayush Kumar</span>
    </h1>
    
    <div class="h-12 md:h-16 flex items-center justify-center mb-8">
      <span class="text-xl md:text-3xl text-muted font-mono">
        {displayText}<span class="animate-pulse">|</span>
      </span>
    </div>
    
    <p class="text-lg md:text-xl text-muted max-w-2xl mx-auto mb-10">
      Student • Unity Developer • Future Software Engineer
    </p>
    
    <div class="flex flex-col sm:flex-row gap-4 justify-center mb-16">
      <a href="#projects" class="btn-primary">View Projects</a>
      <a href="#contact" class="btn-secondary">Contact Me</a>
    </div>
    
    <div class="hidden md:flex justify-center gap-8">
      {#each floatingCards as card}
        <div 
          class="glass-card animate-float flex items-center gap-3"
          style="animation-delay: {card.delay};"
        >
          <span class="text-2xl">{card.icon}</span>
          <span class="font-medium">{card.label}</span>
        </div>
      {/each}
    </div>
  </div>
  
  <div class="absolute bottom-10 left-1/2 -translate-x-1/2 animate-bounce">
    <svg class="w-6 h-6 text-muted" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
    </svg>
  </div>
</section>

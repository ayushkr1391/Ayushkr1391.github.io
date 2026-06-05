<script lang="ts">
  import SectionTitle from '$lib/components/SectionTitle.svelte';
  
  const projects = [
    {
      title: 'Personal Portfolio',
      description: 'A modern, responsive portfolio website built with SvelteKit, TypeScript, and Tailwind CSS featuring glassmorphism design and smooth animations.',
      tech: ['SvelteKit', 'TypeScript', 'Tailwind'],
      image: '🌐',
      github: 'https://github.com/ayushkr1391',
      live: '#'
    },
    {
      title: 'Unity Game Project',
      description: 'An engaging game developed in Unity with C#, featuring custom mechanics, optimized performance, and immersive gameplay experiences.',
      tech: ['Unity', 'C#', 'DOTS'],
      image: '🎮',
      github: 'https://github.com/ayushkr1391',
      live: null
    },
    {
      title: 'Svelte Web Application',
      description: 'A dynamic web application showcasing modern Svelte features, reactive state management, and responsive design principles.',
      tech: ['Svelte', 'JavaScript', 'CSS'],
      image: '⚡',
      github: 'https://github.com/ayushkr1391',
      live: null
    },
    {
      title: 'Future Projects',
      description: 'Exciting projects in development! Stay tuned for more innovative applications, games, and tools coming soon.',
      tech: ['Coming Soon'],
      image: '🚀',
      github: null,
      live: null
    }
  ];
</script>

<section id="projects" class="relative py-24 px-4">
  <div class="max-w-6xl mx-auto">
    <SectionTitle title="My Projects" subtitle="What I've built" />
    
    <div class="grid md:grid-cols-2 gap-6">
      {#each projects as project, i}
        <div 
          class="glass-card glow-hover group"
          style="animation: fadeInUp 0.5s ease {i * 0.15}s both;"
        >
          <div class="aspect-video bg-gradient-to-br from-primary/10 via-accent/10 to-secondary/10 rounded-xl mb-4 flex items-center justify-center">
            <span class="text-6xl group-hover:scale-110 transition-transform duration-300">{project.image}</span>
          </div>
          
          <h3 class="text-xl font-bold mb-2 group-hover:text-primary transition-colors">{project.title}</h3>
          <p class="text-muted text-sm mb-4 leading-relaxed">{project.description}</p>
          
          <div class="flex flex-wrap gap-2 mb-4">
            {#each project.tech as tech}
              <span class="px-3 py-1 text-xs font-medium bg-primary/10 text-primary rounded-full">{tech}</span>
            {/each}
          </div>
          
          <div class="flex gap-3">
            {#if project.github}
              <a 
                href={project.github} 
                target="_blank" 
                rel="noopener noreferrer"
                class="flex items-center gap-2 px-4 py-2 glass hover:bg-white/10 rounded-lg text-sm font-medium transition-all"
              >
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
                GitHub
              </a>
            {/if}
            {#if project.live}
              <a 
                href={project.live} 
                target="_blank" 
                rel="noopener noreferrer"
                class="flex items-center gap-2 px-4 py-2 bg-primary hover:bg-primary/90 rounded-lg text-sm font-medium transition-all"
              >
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"/></svg>
                Live Demo
              </a>
            {/if}
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
</style>

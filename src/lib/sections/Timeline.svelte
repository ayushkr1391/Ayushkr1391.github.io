<script lang="ts">
  import SectionTitle from '$lib/components/SectionTitle.svelte';
  
  const timeline = [
    {
      year: '2021',
      title: 'Started Coding',
      description: 'Began my programming journey with curiosity and passion for technology.',
      icon: '🚀'
    },
    {
      year: '2022',
      title: 'Web Development',
      description: 'Learned HTML, CSS, and JavaScript to build interactive websites.',
      icon: '🌐'
    },
    {
      year: '2023',
      title: 'Unity Development',
      description: 'Started game development with Unity and C#, exploring DOTS for performance.',
      icon: '🎮'
    },
    {
      year: '2024',
      title: 'Learning SvelteKit',
      description: 'Diving deep into modern frameworks like SvelteKit and TypeScript.',
      icon: '⚡'
    },
    {
      year: 'Future',
      title: 'Software Engineering',
      description: 'Working towards becoming a professional software engineer building impactful products.',
      icon: '🎯'
    }
  ];
</script>

<section id="timeline" class="relative py-24 px-4">
  <div class="max-w-4xl mx-auto">
    <SectionTitle title="My Journey" subtitle="Learning timeline" />
    
    <div class="relative">
      <div class="absolute left-4 md:left-1/2 top-0 bottom-0 w-0.5 bg-gradient-to-b from-primary via-accent to-secondary"></div>
      
      {#each timeline as item, i}
        <div 
          class="relative flex items-center mb-12 {i % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse'}"
          style="animation: fadeInUp 0.5s ease {i * 0.2}s both;"
        >
          <div class="absolute left-4 md:left-1/2 w-4 h-4 -ml-2 bg-primary rounded-full glow z-10"></div>
          
          <div class="ml-12 md:ml-0 md:w-1/2 {i % 2 === 0 ? 'md:pr-12 md:text-right' : 'md:pl-12'}">
            <div class="glass-card glow-hover">
              <div class="flex items-center gap-3 mb-2 {i % 2 === 0 ? 'md:flex-row-reverse' : ''}">
                <span class="text-3xl">{item.icon}</span>
                <span class="px-3 py-1 text-sm font-bold bg-primary/20 text-primary rounded-full">{item.year}</span>
              </div>
              <h3 class="text-xl font-bold mb-2">{item.title}</h3>
              <p class="text-muted text-sm">{item.description}</p>
            </div>
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

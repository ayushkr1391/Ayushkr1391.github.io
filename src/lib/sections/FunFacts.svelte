<script lang="ts">
  import SectionTitle from '$lib/components/SectionTitle.svelte';
  
  const facts = [
    { icon: '💻', title: 'Tech Enthusiast', description: 'Always excited about new technologies and frameworks' },
    { icon: '🎮', title: 'Game Developer', description: 'Passionate about creating immersive gaming experiences' },
    { icon: '📚', title: 'Continuous Learner', description: 'Dedicated to learning something new every day' },
    { icon: '🚀', title: 'Project Builder', description: 'Love turning ideas into real, working applications' }
  ];
</script>

<section class="relative py-24 px-4">
  <div class="max-w-6xl mx-auto">
    <SectionTitle title="Fun Facts" subtitle="A bit more about me" />
    
    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
      {#each facts as fact, i}
        <div 
          class="glass-card text-center glow-hover group"
          style="animation: fadeInUp 0.5s ease {i * 0.1}s both;"
        >
          <span class="text-5xl mb-4 block group-hover:scale-110 transition-transform duration-300">{fact.icon}</span>
          <h3 class="text-lg font-bold mb-2">{fact.title}</h3>
          <p class="text-muted text-sm">{fact.description}</p>
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

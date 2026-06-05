<script lang="ts">
  import SectionTitle from '$lib/components/SectionTitle.svelte';
  
  const skills = [
    { name: 'Unity', icon: '🎮', level: 75, color: 'from-purple-500 to-pink-500' },
    { name: 'C#', icon: '💜', level: 70, color: 'from-violet-500 to-purple-500' },
    { name: 'DOTS', icon: '⚡', level: 45, color: 'from-yellow-500 to-orange-500' },
    { name: 'Svelte', icon: '🔥', level: 60, color: 'from-orange-500 to-red-500' },
    { name: 'Tailwind CSS', icon: '💨', level: 80, color: 'from-cyan-500 to-blue-500' },
    { name: 'HTML', icon: '📄', level: 90, color: 'from-orange-400 to-red-400' },
    { name: 'CSS', icon: '🎨', level: 85, color: 'from-blue-400 to-indigo-500' },
    { name: 'JavaScript', icon: '⚡', level: 70, color: 'from-yellow-400 to-yellow-600' },
    { name: 'Git', icon: '📦', level: 65, color: 'from-red-500 to-orange-500' },
    { name: 'GitHub', icon: '🐙', level: 70, color: 'from-gray-600 to-gray-800' }
  ];
</script>

<section id="skills" class="relative py-24 px-4">
  <div class="max-w-6xl mx-auto">
    <SectionTitle title="My Skills" subtitle="Technologies I work with" />
    
    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-4">
      {#each skills as skill, i}
        <div 
          class="glass-card group cursor-default"
          style="animation: fadeInUp 0.5s ease {i * 0.1}s both;"
        >
          <div class="text-4xl mb-3">{skill.icon}</div>
          <h3 class="font-semibold mb-3">{skill.name}</h3>
          <div class="w-full h-2 bg-white/10 rounded-full overflow-hidden">
            <div 
              class="h-full bg-gradient-to-r {skill.color} rounded-full transition-all duration-1000"
              style="width: {skill.level}%;"
            ></div>
          </div>
          <span class="text-sm text-muted mt-2 block">{skill.level}%</span>
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

<script lang="ts">
  import SectionTitle from '$lib/components/SectionTitle.svelte';
  
  const stats = [
    { label: 'Repositories', value: '10+' },
    { label: 'Commits', value: '100+' },
    { label: 'Languages', value: '5+' }
  ];
  
  const contributionGrid = Array(7).fill(null).map(() => 
    Array(12).fill(null).map(() => Math.floor(Math.random() * 4))
  );
</script>

<section id="github" class="relative py-24 px-4">
  <div class="max-w-6xl mx-auto">
    <SectionTitle title="GitHub Activity" subtitle="My coding journey" />
    
    <div class="grid md:grid-cols-2 gap-8">
      <div class="glass-card glow">
        <div class="flex items-center gap-4 mb-6">
          <div class="w-16 h-16 bg-gradient-to-br from-primary to-accent rounded-full flex items-center justify-center">
            <span class="text-3xl">🐙</span>
          </div>
          <div>
            <h3 class="text-xl font-bold">ayushkr1391</h3>
            <p class="text-muted text-sm">Student Developer</p>
          </div>
        </div>
        
        <div class="grid grid-cols-3 gap-4 mb-6">
          {#each stats as stat}
            <div class="text-center p-3 bg-white/5 rounded-xl">
              <p class="text-2xl font-bold gradient-text">{stat.value}</p>
              <p class="text-xs text-muted">{stat.label}</p>
            </div>
          {/each}
        </div>
        
        <a 
          href="https://github.com/ayushkr1391" 
          target="_blank" 
          rel="noopener noreferrer"
          class="btn-primary w-full text-center block"
        >
          View GitHub Profile
        </a>
      </div>
      
      <div class="glass-card">
        <h4 class="font-semibold mb-4">Contribution Activity</h4>
        <div class="overflow-x-auto">
          <div class="flex flex-col gap-1">
            {#each contributionGrid as row}
              <div class="flex gap-1">
                {#each row as level}
                  <div 
                    class="w-3 h-3 rounded-sm transition-colors {
                      level === 0 ? 'bg-white/5' :
                      level === 1 ? 'bg-primary/30' :
                      level === 2 ? 'bg-primary/60' :
                      'bg-primary'
                    }"
                  ></div>
                {/each}
              </div>
            {/each}
          </div>
        </div>
        <div class="flex items-center gap-2 mt-4 text-xs text-muted">
          <span>Less</span>
          <div class="w-3 h-3 rounded-sm bg-white/5"></div>
          <div class="w-3 h-3 rounded-sm bg-primary/30"></div>
          <div class="w-3 h-3 rounded-sm bg-primary/60"></div>
          <div class="w-3 h-3 rounded-sm bg-primary"></div>
          <span>More</span>
        </div>
      </div>
    </div>
  </div>
</section>

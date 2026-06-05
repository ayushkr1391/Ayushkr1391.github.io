<script lang="ts">
  import { onMount } from 'svelte';
  
  let progress = $state(0);
  
  onMount(() => {
    const updateProgress = () => {
      const scrollHeight = document.documentElement.scrollHeight - window.innerHeight;
      progress = (window.scrollY / scrollHeight) * 100;
    };
    
    window.addEventListener('scroll', updateProgress);
    return () => window.removeEventListener('scroll', updateProgress);
  });
</script>

<div class="fixed top-0 left-0 right-0 h-1 z-[60] bg-background/50">
  <div 
    class="h-full bg-gradient-to-r from-primary via-accent to-secondary transition-all duration-150"
    style="width: {progress}%"
  ></div>
</div>

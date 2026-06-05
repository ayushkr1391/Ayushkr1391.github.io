<script lang="ts">
  import SectionTitle from '$lib/components/SectionTitle.svelte';
</script>

<section id="about" class="relative py-24 px-4">
  <div class="max-w-6xl mx-auto">
    <SectionTitle title="About Me" subtitle="Get to know me better" />
    
    <div class="grid md:grid-cols-2 gap-12 items-center">
      <div class="relative">
        <div class="glass-card glow">
          <div class="w-full aspect-square bg-gradient-to-br from-primary/20 via-accent/20 to-secondary/20 rounded-xl flex items-center justify-center">
            <span class="text-8xl">👨‍💻</span>
          </div>
        </div>
        <div class="absolute -bottom-4 -right-4 glass px-4 py-2">
          <span class="text-primary font-bold">Class 11</span>
        </div>
      </div>
      
      <div class="space-y-6">
        <h3 class="text-2xl md:text-3xl font-bold">
          Passionate about <span class="gradient-text">Technology</span>
        </h3>
        
        <p class="text-muted leading-relaxed">
          {"I'm a Class 11 student with a deep passion for technology and programming. My journey into the world of coding started with curiosity and has grown into a dedicated pursuit of becoming a software engineer."}
        </p>
        
        <p class="text-muted leading-relaxed">
          {"I'm particularly interested in game development using Unity, web technologies, and building impactful digital products. Every day, I'm learning something new and pushing my boundaries to become better at what I do."}
        </p>
        
        <p class="text-muted leading-relaxed">
          My goal is to become a software engineer and create products that make a difference in {"people's"} lives. {"I believe in continuous learning and I'm always excited to take on new challenges."}
        </p>
        
        <div class="flex flex-wrap gap-4 pt-4">
          <div class="glass px-4 py-2">
            <span class="text-sm text-muted">Location</span>
            <p class="font-medium">India</p>
          </div>
          <div class="glass px-4 py-2">
            <span class="text-sm text-muted">Education</span>
            <p class="font-medium">Class 11</p>
          </div>
          <div class="glass px-4 py-2">
            <span class="text-sm text-muted">Focus</span>
            <p class="font-medium">Game Dev & Web</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

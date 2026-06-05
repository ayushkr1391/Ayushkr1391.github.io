<script lang="ts">
  import SectionTitle from '$lib/components/SectionTitle.svelte';
  
  let formData = $state({ name: '', email: '', message: '' });
  let status = $state<'idle' | 'success'>('idle');
  
  function handleSubmit(e: Event) {
    e.preventDefault();
    status = 'success';
    formData = { name: '', email: '', message: '' };
    setTimeout(() => status = 'idle', 3000);
  }
</script>

<section id="contact" class="relative py-24 px-4">
  <div class="max-w-4xl mx-auto">
    <SectionTitle title="Get In Touch" subtitle="Let's connect" />
    
    <div class="grid md:grid-cols-2 gap-8">
      <div class="space-y-6">
        <h3 class="text-2xl font-bold">{"Let's work together!"}</h3>
        <p class="text-muted leading-relaxed">
          {"I'm always open to discussing new projects, creative ideas, or opportunities to be part of your vision. Feel free to reach out!"}
        </p>
        
        <div class="space-y-4">
          <a 
            href="https://github.com/ayushkr1391" 
            target="_blank" 
            rel="noopener noreferrer"
            class="flex items-center gap-4 glass-card"
          >
            <div class="w-12 h-12 bg-primary/20 rounded-xl flex items-center justify-center">
              <svg class="w-6 h-6 text-primary" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
            </div>
            <div>
              <p class="font-medium">GitHub</p>
              <p class="text-sm text-muted">@ayushkr1391</p>
            </div>
          </a>
          
          <a 
            href="https://www.instagram.com/_ayush____69" 
            target="_blank" 
            rel="noopener noreferrer"
            class="flex items-center gap-4 glass-card"
          >
            <div class="w-12 h-12 bg-accent/20 rounded-xl flex items-center justify-center">
              <svg class="w-6 h-6 text-accent" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
            </div>
            <div>
              <p class="font-medium">Instagram</p>
              <p class="text-sm text-muted">@_ayush____69</p>
            </div>
          </a>
        </div>
      </div>
      
      <form onsubmit={handleSubmit} class="glass-card">
        {#if status === 'success'}
          <div class="text-center py-8">
            <span class="text-5xl mb-4 block">✅</span>
            <p class="text-lg font-medium text-primary">Message sent successfully!</p>
          </div>
        {:else}
          <div class="space-y-4">
            <div>
              <label for="name" class="block text-sm font-medium mb-2">Name</label>
              <input 
                type="text" 
                id="name" 
                bind:value={formData.name}
                required
                class="w-full px-4 py-3 bg-white/5 border border-white/10 rounded-xl focus:border-primary focus:outline-none transition-colors"
                placeholder="Your name"
              />
            </div>
            <div>
              <label for="email" class="block text-sm font-medium mb-2">Email</label>
              <input 
                type="email" 
                id="email" 
                bind:value={formData.email}
                required
                class="w-full px-4 py-3 bg-white/5 border border-white/10 rounded-xl focus:border-primary focus:outline-none transition-colors"
                placeholder="your@email.com"
              />
            </div>
            <div>
              <label for="message" class="block text-sm font-medium mb-2">Message</label>
              <textarea 
                id="message" 
                bind:value={formData.message}
                required
                rows="4"
                class="w-full px-4 py-3 bg-white/5 border border-white/10 rounded-xl focus:border-primary focus:outline-none transition-colors resize-none"
                placeholder="Your message..."
              ></textarea>
            </div>
            <button type="submit" class="btn-primary w-full">
              Send Message
            </button>
          </div>
        {/if}
      </form>
    </div>
  </div>
</section>

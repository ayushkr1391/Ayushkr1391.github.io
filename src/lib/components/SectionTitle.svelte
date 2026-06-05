<script lang="ts">
  interface Props {
    title: string;
    subtitle?: string;
  }
  
  let { title, subtitle }: Props = $props();
</script>

<div class="text-center mb-16">
  {#if subtitle}
    <span class="inline-block px-4 py-1 glass text-sm text-primary mb-4">{subtitle}</span>
  {/if}
  <h2 class="text-3xl md:text-4xl font-bold">{title}</h2>
</div>

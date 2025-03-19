<script lang="ts">
  import type { Snippet } from "svelte";

  interface ComponentProps {
    children: Snippet;
    isSecondary?: boolean;
    onclick?: (e: MouseEvent) => void;
    type?: "submit" | "button";
  }

  let { children, isSecondary, onclick, ...props }: ComponentProps = $props();
</script>

{#if isSecondary}
  <button
    {...props}
    {onclick}
    class="min-w-15 text-gray p-3 cursor-pointer text-2xl font-bold"
    >{@render children()}</button
  >
{:else}
  <button
    {...props}
    class="w-full flex gap-x-3 justify-center px-3 py-2 cursor-pointer bg-primary rounded-2xl text-light-yellow text-2xl font-bold"
    {onclick}
  >
    {@render children()}
  </button>
{/if}

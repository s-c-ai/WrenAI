<script lang="ts">
  import Icon from "@iconify/svelte";
  import { Button } from "$components";

  interface ComponentProps {
    image: string;
    title: string;
    description: string;
    needUpdate?: boolean;
  }

  let { image, title, description, needUpdate }: ComponentProps = $props();
</script>

<div class="app-container min-w-46 max-w-69 h-62 p-2 flex flex-col">
  <div class="text-end w-full">
    <Button isSecondary={true}
      ><Icon
        icon="material-symbols:more-horiz"
        width="24"
        height="24"
      /></Button
    >
  </div>
  <div class="flex justify-between mt-2">
    <img src={image} alt="" />
    {#if needUpdate}
      <div class="update flex items-center gap-x-3">
        <Icon icon="material-symbols:update" />
        <p class="text-secondary">Update</p>
      </div>
    {:else}
      <div class="installed flex items-center gap-x-3">
        <Icon icon="material-symbols:check-rounded" />
        <p class="text-green">Installed</p>
      </div>
    {/if}
  </div>
  <h2 class="text-dark-blue font-medium text-2xl mt-2">{title}</h2>
  <p class="text-xs mt-2 overflow-hidden text-ellipsis">{description}</p>
</div>

<style>
  :global(.installed svg) {
    color: var(--color-green);
  }
  :global(.update svg) {
    color: var(--color-secondary);
  }

  .app-container {
    border-radius: 20px;
    border: 1px solid rgba(89, 89, 89, 0.2);
  }
</style>

<script lang="ts">
  import Icon from "@iconify/svelte";
  import { Button } from "$components";
  import logoImage from "$assets/logo.svg";
  import { goto } from "$app/navigation";
</script>

<nav class="header-container px-10 flex justify-between w-full items-center">
  <div class="flex w-full">
    <img src={logoImage} alt="" class="mr-9" />
    <div class="flex items-center">
      <div
        class="flex flex-col sm:flex-row w-full gap-x-3 sm:items-end items-center"
      >
        <h2 class="text-dark-blue font-medium text-2xl">App Hub</h2>
        <p class="text-lg">Welcome Back!</p>
      </div>
    </div>
  </div>
  <Button
    onclick={() => {
      goto("/");
    }}
    isSecondary={true}
    ><Icon icon="material-symbols:exit-to-app" width="60" height="60" /></Button
  >
</nav>

<style>
  .header-container {
    border-bottom: 1px solid rgba(89, 89, 89, 0.2);
  }
</style>

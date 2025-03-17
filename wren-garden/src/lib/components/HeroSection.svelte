<script lang="ts">
  import { AuthForm } from "$components";
  import heroImage from "$assets/gradient.svg";
</script>

<section class="flex flex-col h-screen sm:px-14">
  <div class="flex w-full h-full items-center justify-between">
    <div class="flex flex-col w-9/20">
      <h1 class="text-dark-blue font-bold text-5xl mb-6">
        Intelligent, Efficient and <br />Productive
      </h1>
      <h2 class="text-dark-blue font-medium text-2xl">
        An AI Applications Hub
      </h2>
    </div>
    <div class="w-9/20 h-3/4"><AuthForm /></div>
  </div>
  <div
    class="flex w-full justify-center gap-10 fixed bottom-0 mb-10 sm:justify-start"
  >
    <a class="text-primary font-bold text-xs" href="mailto:contato@s-c.ai"
      >Contact Us</a
    >
    <a class="text-primary font-bold text-xs" href="https://s-c.ai"
      >Our website</a
    >
  </div>
</section>

<script lang="ts">
  import logoImage from "$assets/logo-with-text.svg";
  import { Button } from "$components";

  let isRegistration = $state(false);

  const toogleRegistration = () => {
    isRegistration = !isRegistration;
  };
</script>

<div
  class="px-15 py-31 auth-border flex flex-col justify-center w-full h-full items-start"
>
  <img src={logoImage} alt="" class="mb-10 w-100 h-20" />
  {#if isRegistration}
    <h1 class="text-dark-blue font-bold text-5xl mb-6">Sign Up</h1>
    <h2 class="text-dark-blue font-medium text-2xl mb-10">Welcome!</h2>
  {:else}
    <h1 class="text-dark-blue font-bold text-5xl mb-6">
      Log in to your account
    </h1>
    <h2 class="text-dark-blue font-medium text-2xl mb-10">Welcome back!</h2>
  {/if}
  <form
    action=""
    method="POST"
    class="auth-form flex flex-col w-full h-full items-start"
  >
    <input type="text" placeholder="Email" name="email" />
    <input type="password" placeholder="Password" name="password" />
    {#if isRegistration}
      <input
        type="password"
        placeholder="Confirm password"
        name="passwordConfirm"
      />
    {/if}
    <div class="w-full text-center">
      <Button>{isRegistration ? "Sign up" : "Login"}</Button>
    </div>
    {#if isRegistration}
      <p class="text-dark-blue text-xs mt-6">
        Already have an account? <button
          class="text-primary font-bold text-xs cursor-pointer"
          onclick={toogleRegistration}>Sign in</button
        >
      </p>
    {:else}
      <p class="text-dark-blue text-xs mt-6">
        Don't have an account? <button
          class="text-primary font-bold text-xs cursor-pointer"
          onclick={toogleRegistration}>Sign up</button
        >
      </p>
    {/if}
  </form>
</div>

<style>
  .auth-form input {
    font-size: 12px;
    padding: 12px;
    width: 100%;
    border-radius: 16px;
    border: 1px solid var(--color-gray);
    margin-bottom: 20px;
  }

  .auth-form input:focus {
    outline: none;
  }

  .auth-form input:last-of-type {
    margin-bottom: 40px;
  }

  .auth-border {
    border-image: linear-gradient(
        21deg,
        rgba(253, 253, 253, 1) 60%,
        rgba(253, 200, 49, 1) 100%
      )
      1;
    border-width: 1px;
    border-style: solid;
    border-radius: 12px;
  }
</style>

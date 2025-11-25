<script setup lang="ts">

import AppMenu from "./appMenu.vue";
</script>

<template>
  <div class="wrapper bg--transparent">
    <div class="app-bar container margin-auto">
      <img src="/img/logo_white.svg" alt="logo" class="logo"/>
      <app-menu class="app-menu"/>
      <nuxt-link class="font-medium link" to="#">Become a Seller</nuxt-link>
      <nuxt-link class="font-medium link link" id="btn--sign-in" to="#">Sign in</nuxt-link>
      <button class="btn--featured btn--rounded">Join</button>
    </div>
  </div>
</template>

<style scoped>
@layer modules {
  .app-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-inline: var(--default-padding);
  }

  .app-menu {
    flex: 1;
    display: flex;
    justify-content: center;
    color: white;
    align-self: stretch;
    gap: 1.5rem;
  }

  .link {
    color: white;
    margin-inline-end: 1rem;
    display: none;

    &:hover {
      color: var(--primary-color);
    }

    @media (min-width: 993px) {
      display: block;
    }
  }

  #btn--sign-in {
    display: none;

    @media (min-width: 1200px) {
      display: block;
    }
  }
}
</style>
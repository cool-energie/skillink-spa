<script setup lang="ts">

import AppMenu from "./appMenu.vue";
</script>

<template>
    <div class="app-bar">
      <img src="/img/logo_white.svg" alt="logo" class="logo" />
      <app-menu class="app-menu" />
      <button class="btn--featured rounded">Join</button>
    </div>
</template>

<style scoped>
@layer modules {
  .app-bar {
    background-color: grey;
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
}
</style>
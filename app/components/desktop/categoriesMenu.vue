<script setup lang="ts">

</script>

<template>
<div class="categories-menu">
  <button class="btn--rounded bg--transparent activator font-medium color--white">
    <img src="/img/cat_btn_ic.svg" alt="cat_icon" /> Categories
  </button>
</div>
</template>

<style scoped>
@layer modules {
  .categories-menu {
    align-items: center;
    display: none;

    @media (min-width: 1200px) {
      display: flex;
    }
  }
  .activator {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
}

</style>
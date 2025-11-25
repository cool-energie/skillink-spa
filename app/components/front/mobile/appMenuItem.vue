<script setup lang="ts">
defineProps(["label", "url"])
</script>

<template>
  <NuxtLink class="menu-item" href="#">
    <span class="font-medium">{{label}}</span>
    <img src="/img/arrow_right.svg" alt="arrow" />
  </NuxtLink>
</template>

<style scoped>
@layer modules {
  .menu-item {
    padding: var(--default-padding);
    display: flex;
    justify-content: space-between;
    align-items: center;

    &:active {
      border-inline-start: 2px solid var(--primary-color);
      padding-inline-start: calc(var(--default-padding) - 2px);
      background-color: var(--light-grey);
    }
  }
}
</style>
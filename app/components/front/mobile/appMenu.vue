<script setup lang="ts">
  import AppMenuItem from "./appMenuItem.vue";

  const menuItems = [
    {
      label: "Home",
      url: "#",
    },
    {
      label: "Browse Jobs",
      url: "#",
    },
    {
      label: "Services",
      url: "#",
    },
    {
      label: "Blog",
      url: "#",
    },
    {
      label: "Pages",
      url: "#",
    },
    {
      label: "Contact",
      url: "#",
    },
  ]
</script>

<template>
  <nav>
    <app-menu-item v-for="item in menuItems" :label="item.label" :url="item.url" />
  </nav>
</template>

<style scoped>

</style>
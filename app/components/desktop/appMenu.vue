<script setup lang="ts">
import CategoriesMenu from "./categoriesMenu.vue";

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
  <div>
    <categories-menu />
    <nuxt-link v-for="item in menuItems" :to="item.url" class="font-medium">
      {{ item.label }}
    </nuxt-link>
  </div>
</template>

<style scoped>
@layer modules {
  .font-medium {
    display: flex;
    align-items: center;
    border: 2px solid transparent;
    padding-block: var(--default-padding);
    &:active, &:hover {
      border-top: 2px solid var(--primary-color);
    }
  }
}
</style>
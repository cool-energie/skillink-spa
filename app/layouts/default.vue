<script setup lang="ts">

import MobileAppBar from "../components/front/mobile/appBar.vue";
import DesktopAppBar from "../components/front/desktop/appBar.vue";
</script>

<template>
  <mobile-app-bar class="mobile-app-bar" />
  <desktop-app-bar class="desktop-app-bar" />
<slot />
</template>

<style scoped>
@layer modules {
  .mobile-app-bar {
    display: flex;
  }
  .desktop-app-bar {
    display: none;
  }
  @media (min-width: 768px) {
    .mobile-app-bar {
      display: none;
    }
    .desktop-app-bar {
      display: block;
    }
  }
}
</style>
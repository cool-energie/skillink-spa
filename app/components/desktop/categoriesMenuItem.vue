<script setup lang="ts">
import {computed, watch} from "vue";

  const props = defineProps({
    active: { type: Boolean },
    iconSrc: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
  })

  const classes = computed(() => props.active ? ["active"] : [])
</script>

<template>
<div :class="classes" class="categories-menu-item font-medium">
  <img :src="iconSrc" alt="icon">
  <span>{{ name }}</span>
</div>
</template>

<style scoped>
@layer modules {
  .categories-menu-item {
    padding: 1rem 2rem;
    display: flex;
    gap: 1rem;
    align-items: center;
    border-inline-start: 2px solid transparent;
    cursor: pointer;

    &:hover, &.active {
      border-color: var(--primary-color);
      background-color: var(--light-grey);
    }
  }
}
</style>
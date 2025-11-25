<script setup lang="ts">
  defineProps({
    logo: {
      type: String,
      required: true,
    },
    nbSkills: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    subCategories: {
      type: Array,
      required: true,
    }
  })
</script>

<template>
<div class="category-card card">
  <img :src="`/img/${logo}`" />
  <span>{{nbSkills}} skills</span>
  <span>{{name}}</span>
  <span>{{ subCategories.join(",")}}</span>
</div>
</template>

<style scoped>

</style>
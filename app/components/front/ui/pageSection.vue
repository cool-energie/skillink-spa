<script setup lang="ts">
defineProps({
  bgColor: {
    type: String,
    default: "#FFF",
  },
  title: {
    type: String,
  },
  subTitle: {
    type: String,
  },
  link: {
    type: Object
  }
})
</script>

<template>
  <div class="page-section" :style="`background-color: ${bgColor};`">
    <section class="container">
      <div>
        <h2 v-if="title">{{ title }}</h2>
        <p v-if="subTitle" class="sub-title sub-text">{{ subTitle }}</p>
      </div>
      <a v-if="link" :href="link.to" class="sub-text title-link font-bold">{{ link.text }} <img
          src="/img/link-arrow-right.svg" alt=""/></a>
      <slot/>
    </section>
  </div>
</template>

<style scoped>
@layer modules {
  section {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    overflow-x: clip;
    padding: var(--default-padding);

    h2, p {
      margin-block: 0;
    }
  }

  .title-link {
    display: flex;
    align-items: center;
    gap: .5em;

    img {
      width: 1.25em;
      height: 1.25em;
    }
  }
}
</style>
<script setup lang="ts">
  defineProps({
    items: Array,
  })
</script>

<template>
  <div class="categories-menu-items-detail">
    <div v-for="item in items" :key="item.group">
      <span class="categories-menu-items-detail--group">{{ item.group }}</span>
      <ul>
        <li class="categories-menu-items-detail--item font-regular" v-for="cat in item.items">
          <nuxt-link href="#">{{ cat }}</nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
@layer modules {
  .categories-menu-items-detail {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5rem;
    grid-auto-flow: dense;
    padding: var(--default-padding);
    position: absolute;
    left: 100%;
    top: -1px;
    width: 50rem;
    background-color: #FFF;
    border: 1px solid var(--grey-border-color);
    box-shadow: var(--light-grey) -1px 0 1px;

    > div {
      display: flex;
      flex-direction: column;
      gap: .875rem;

      ul {
        display: flex;
        flex-direction: column;
        gap: .5rem;
      }
    }
  }
  .categories-menu-items-detail--item {
    font-size: .875rem;
    color: var(--grey-font-color);

    a:hover {
      color: var(--font-black-color);
    }
  }
}
</style>
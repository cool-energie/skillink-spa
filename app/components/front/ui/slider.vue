<script setup lang="ts">
import {computed, ref} from "vue";

const props = defineProps({
  nbItems: {
    type: Number,
    required: true,
  },
  perPage: {
    type: Number,
    required: true,
  },
  items: {
    type: Array<Object>,
    required: true,
  }
})
const page = ref(1)
const nbPage = Math.ceil(props.nbItems / props.perPage)

function moveNext() {
  if (page.value < nbPage) page.value++
}

function movePrev() {
  if (page.value > 1) page.value--
}

const sliderStyle = computed(() => ({
  transform: `translateX(-${(page.value - 1) * 100}%)`
}))
</script>

<template>
  <div class="slider-wrapper">
    <div class="slider" :style="sliderStyle">
      <div v-for="item in items">
        <slot name="item" v-bind="item"/>
      </div>
    </div>
    <div class="pagination">
      <button @click="movePrev" :disabled="page === 1" class="bg--transparent"><img src="/img/link-arrow-left.svg" alt=""/></button>
      <div class="page-dots">
        <div v-for="i in nbPage" :key="i" class="page-dot" :class="page === i ? 'active' : ''"></div>
      </div>
      <button @click="moveNext" :disabled="page === nbPage" class="bg--transparent"><img src="/img/link-arrow-right.svg" alt=""/></button>
    </div>
  </div>
</template>

<style scoped>
@layer modules {
  .slider-wrapper {
    overflow-x: clip;
    display: flex;
    flex-direction: column;
    gap: 1.25em;
  }
  .slider {
    display: flex;
    width: 100%;

    > * {
      flex-shrink: 0;
      flex-basis: 100%;
    }
  }
  .pagination {
    display: flex;
    align-items: center;

    button {
      display: flex;
      align-items: center;
    }
  }

  .page-dots {
    display: flex;
    gap: .8em;
    align-items: center;
  }

  .page-dot {
    width: 8px;
    height: 8px;
    background-color: var(--light-grey);
    border-radius: 4px;

    &.active {
      background-color: var(--font-black-color);
    }
  }
}
</style>
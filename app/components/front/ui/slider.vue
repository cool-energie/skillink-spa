<script setup lang="ts">
import {tns} from "tiny-slider";
import {onMounted} from "vue";

const slider = useState("slider--slider", () => null)
const nbSlides = useState("slider--nbSlides", () => null)
const slidePerPage = useState("slider--slidePerPage", () => null)
const nbPage = useState("slider--nbPage", () => null)
onMounted(() => {
  slider.value = tns({
    container: '.slider',
    slideBy: 'page'
  })
  nbSlides.value = slider.value?.getInfo()?.slideCount
  slidePerPage.value = slider.value?.getInfo()?.items
  nbPage.value = Math.ceil(nbSlides.value / slidePerPage.value)
})
</script>

<template>
  <div class="slider-wrapper">
    <div class="slider">
      <slot/>
    </div>
    <div class="pagination">
      <a><img src="/img/link-arrow-left.svg" alt=""/></a>
      <!--div v-for="i in nbPage" :key="i" class="page-dot"></div-->
      <a><img src="/img/link-arrow-right.svg" alt=""/></a>
    </div>
  </div>
</template>

<style scoped>

</style>
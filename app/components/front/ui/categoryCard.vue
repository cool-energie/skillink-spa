<script setup lang="ts">
const props = defineProps({
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
const formatedSubcategories = getFormatedSubcategories()
function getFormatedSubcategories() {
  var subcategories = props.subCategories.join(", ")
  if(subcategories.length > 20) {
    subcategories = subcategories.substring(0, 80).trim()
    var lastSpaceIndex = subcategories.lastIndexOf(" ")
    subcategories = subcategories.substring(0, lastSpaceIndex)
    //test last index is not a punctuation
    var lastIndex = subcategories.length - 1
    if(subcategories[lastIndex] === ",") {
      subcategories = subcategories.substring(0, lastIndex).trim()
    }
    //test last index is not &
    lastIndex = subcategories.length - 1
    if(subcategories[lastIndex] === "&") {
      subcategories = subcategories.substring(0, lastIndex)
      lastSpaceIndex = subcategories.lastIndexOf(" ")
      subcategories = subcategories.substring(0, lastSpaceIndex)
    }

    subcategories = subcategories + " & More"
  }
  return subcategories
}
</script>

<template>
<div class="category-card card">
  <div class="category-card__logo">
    <img class="category-card__logo__img" :src="logo" />
  </div>
  <div class="category-card__text">
    <span class="category-card__text_nb-skills sub-text">{{nbSkills}} skills</span>
    <h3>{{name}}</h3>
    <span>{{ formatedSubcategories }}</span>
  </div>
</div>
</template>

<style scoped>
@layer modules {
  .category-card {
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 1.75em;
  }

  .category-card__logo {
    width: 58px;
    height: 52px;
    background-image: url("/img/bg-logo-elipse.svg");
    background-repeat: no-repeat;
    background-position: right bottom;
  }

  .category-card__logo__img {
    width: 40px;
    height: 40px;
  }

  .category-card__text {
    display: flex;
    flex-direction: column;
    gap: .5em;
  }

  h3 {
    margin-block: 0;
  }
}
</style>
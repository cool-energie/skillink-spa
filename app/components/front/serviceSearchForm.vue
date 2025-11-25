<script setup lang="ts">
const prefix = "service-search-form"
const search = useState(`${prefix}.search`, () => "")
const category = useState(`${prefix}.category`, () => "")
const categoriesList = ["Development & IT", "Design & Creative", "Digital Marketing", "Writing & Translation", "Music & Audio", "Video & Animation", "Engineering & Architecture", "Finance & Accounting"]
</script>

<template>
  <form class="service-search-form">
    <input v-model="search" type="text" id="search" class="search-field block" placeholder="What are you looking for ?">
    <select id="category" class="service-search-form--category" v-model="category">
      <option value="" disabled selected>Select a category</option>
      <option v-for="cat in categoriesList" :value="cat">{{ cat }}</option>
    </select>
    <button class="btn bg--primary">Search</button>
  </form>
</template>

<style scoped>
@layer modules {
  .service-search-form {
    display: flex;
    flex-direction: column;
    gap: 1em;

    @media (min-width: 768px) {
      flex-direction: row;
      gap: .25em;
      padding: .5em;
      background-color: white;
      border-radius: var(--default-radius);
    }

    @media (min-width: 1200px) {
      padding: 1em;
    }
  }
  #search {
    background-image: url(/img/loupe-icon.svg);
    background-repeat: no-repeat;
    background-position: 1em center;
    background-size: 1em;
    padding-inline-start: 2.5em !important;
    border: none;
    border-radius: var(--default-radius);

    @media (min-width: 768px) {
      flex-grow: 1;
    }
  }

  .service-search-form--category {
    display: none;

    @media (min-width: 1200px) {
      display: initial;
      flex-basis: 30%;
      padding-inline: 1.5em;
      border: none;
      border-inline-start: 1px solid var(--grey-border-color);
      appearance: none;
      background-image: url("/img/down-filled-triangular-arrow.svg");
      background-repeat: no-repeat;
      background-position: calc(100% - 1em);
    }
  }
}
</style>
<script setup lang="ts">

import ServiceSearchForm from "./serviceSearchForm.vue";

const popularSearches = "Designer, Developer, Web, IOS, PHP, Senior, Engineer"
</script>

<template>
  <div class="home-hero">
    <div class="container">
      <div class="home-hero__wrapper">
        <div>
          <h1>Hire the best freelancers for any job, online.</h1>
          <p class="sub-text">Millions of people use freeio.com to turn their ideas into reality.</p>
        </div>
        <service-search-form class="service-search-form"/>
        <p class="popular-searches">Popular Searches {{ popularSearches }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
@layer modules {
  .home-hero {
    height: 100vh;
    padding: var(--default-padding);
    color: white;
    background-image: linear-gradient(#22222280, #22222230), url("/img/hero-bg-image-mobile.jpg");
    background-size: cover;
    background-repeat: no-repeat;

    @media (min-width: 768px) {
      margin-top: calc(-40px - 2 * var(--default-padding));
      height: calc(100vh + 40px + 2 * var(--default-padding));
    }

    @media (min-width: 1200px) {
      background-image: linear-gradient(#22222280, #22222230), url("/img/hero-bg-image.jpg");
    }
  }
.container{
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
}
  .home-hero__wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 1rem;
  }

  .popular-searches {
    display: none;
    @media (min-width: 768px) {
      display: block;
    }
  }

  @media (min-width: 1200px) {
    .home-hero__wrapper {
      width: 60%;
    }
  }
}
</style>
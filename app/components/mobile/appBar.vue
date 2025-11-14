<script setup lang="ts">
import {useState} from "nuxt/app";
import AppMenu from "./appMenu.vue";

const appBarClasses = useState<String[]>("appBarClasses", () => [])

function showMenuItems() {
  appBarClasses.value.push("active")
  document.getElementsByTagName("body")[0]?.classList.add("no-scroll")
}

function hideMenuItems() {
  appBarClasses.value = appBarClasses.value.filter(c => c !== "active")
  document.getElementsByTagName("body")[0]?.classList.remove("no-scroll")
}
</script>

<template>
  <div class="app-bar" :class="appBarClasses">
    <img src="/img/logo_white.svg" alt="logo" class="logo" />
    <div class="spacer" />
    <a href="#" class="link--featured font-medium">Join</a>
    <div class="menu__btn" @click="showMenuItems">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="mobile-menu-header">
      <span class="font-medium">Menu</span>
      <button class="close-menu__btn rounded" @click="hideMenuItems">
        <img src="/img/close_icon.svg" alt="close_btn">
      </button>
    </div>
    <app-menu class="app-menu" />
  </div>
</template>

<style scoped>
@layer modules {
  .app-bar {
    background-color: grey;
    display: flex;
    align-items: center;
    padding: var(--default-padding);
    gap: 16px;
    position: relative;

    .mobile-menu-header {
      display: none;
      position: absolute;
      left: 0;
      right: 0;
      height: 100%;
      background-color: white;
      justify-content: space-between;
      padding: var(--default-padding);
      align-items: center;
    }
    .close-menu__btn {
      width: 40px;
      height: 40px;
      background-color: var(--primary-light-color);
      border: 0;
    }

    .app-menu {
      position: absolute;
      top: 100%;
      width: 100%;
      left: 100%;
      background-color: white;
      transition: var(--default-transition);
      height: calc(100vh - 100%);
      overflow-x: scroll;
    }

    &.active {
      .mobile-menu-header {
        display: flex;
      }

      .app-menu {
        left: 0%;
      }
    }
  }
  .menu__btn {
    width: 20px;
    height: 16px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: end;

    span {
      display: block;
      border: 1px solid white;
      width: 100%;

      &:last-child{
        width: 70%;
      }
    }
  }

  .link--featured {
    color: white;
    text-decoration: none;
  }
}
</style>
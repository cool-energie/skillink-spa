<script setup lang="ts">
import CategoriesMenuItem from "./categoriesMenuItem.vue";
import {computed, onMounted} from "vue";
import * as _ from "lodash";
import CategoriesMenuItemsDetail from "./categoriesMenuItemsDetail.vue";

const props = defineProps({
  items: {
    type: Array,
    default: [],
  },
  show: {type: Boolean}
})

const local = useState("categories-menu-items-local-var", () => ({items: []}))
const activeItems = computed(() => local.value.items.filter(it => it.active)[0]?.subCategories);

function itemClikHandler(item) {
    local.value.items.forEach(it => {
      it.active = false
    })
  item.active = true
}

onMounted(() => {
  local.value.items = _.cloneDeep(props.items)
})
</script>

<template>
  <div class="categories-menu-items">
    <categories-menu-item v-for="item in local.items" :active="item.active" :name="item.name" :icon-src="item.icon"
                          @click.stop="itemClikHandler(item)"/>
    <categories-menu-items-detail v-show="activeItems" :items="activeItems" />
  </div>
</template>

<style scoped>
@layer modules {
  .categories-menu-items {
    background-color: #FFF;
    position: absolute;
    top: 90%;
    color: var(--font-black-color);
    width: 330px;
    border: 1px solid var(--grey-border-color);
    border-top-left-radius: var(--default-radius);
    border-bottom-left-radius: var(--default-radius);
  }
}
</style>
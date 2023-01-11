<template>
  <q-menu
    class="sub-menu-wrapper"
    fit
    anchor="top right"
    self="top left"
    scroll-target=".scroll"
  >
      <q-list>
        <template v-for="(currentMenu, index) of parentMenu" :key="index">
          <q-item
            clickable
            @click="handlePageMove(currentMenu)"
          >
            <q-item-section class="menu-list-section">
              <q-item-label>
                {{ currentMenu.meta.title }}
              </q-item-label>
            </q-item-section>
          </q-item>
        </template>
      </q-list>
  </q-menu>
  
</template>

<script setup>
import { ref, computed } from "vue";
import router from "@/router";

const currentMenuList = ref([]);

const props = defineProps({ parentMenu: Object });
const parentMenu = computed(() => props.parentMenu.children);

const handlePageMove = (currentMenu) => {
		router.push(currentMenu.path);
};

</script>

<style>

</style>

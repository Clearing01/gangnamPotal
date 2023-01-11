<template>
	<q-list class="menu-list-wrapper">
		<template v-for="(currentMenu, index) of menu" :key="index">
			<q-item 
				side="left" 
				clickable 
				class="menu-list-container menu-list-parents-wrapper"
				@click="handlePageMove(currentMenu)"
				@mouseenter="mouseOver(true)"
			>
				<q-item-section class="menu-list-section">
					<q-item-label>
						{{ currentMenu.meta.title }}
					</q-item-label>
				</q-item-section>
				<SubDrawer 
					id ="test"
					v-if="currentMenu.children || showValue === true" 
					v-show="showValue"
					:parentMenu="currentMenu"
				/>
			</q-item>
		</template>
	</q-list>
</template>
<script setup lang="ts">
import { computed, ref } from 'vue';
import router from '@/router';
import main from '@/router/main';
import { Router } from 'vue-router';
import SubDrawer from "@/components/SubDrawer.vue";
const showValue = ref(false)

const menu = main;

const handlePageMove = (currentMenu : any) => { 
		router.push(currentMenu.path);
};

const mouseOver = (value : boolean) => {
	// console.log(inputSubMenu)
	// console.log(1,inputSubMenu.meta.isActive)
	// inputSubMenu.meta.isActive = true;
	// console.log(2,inputSubMenu.meta.isActive)
	showValue.value = value;	
}


</script>
<style lang="scss" scoped>
#test {
	visibility: hidden;
	height: 100px;
}
</style>


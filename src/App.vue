<template>
	<section id="container">
		<app-header></app-header>
		<hidden-menu></hidden-menu>
		<app-main></app-main>
	</section>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue';
import AppMain from '@/components/AppMain.vue';
import HiddenMenu from '@/components/HiddenMenu.vue';
export default {
	components: {
		AppHeader,
		AppMain,
		HiddenMenu,
	},
};
</script>
<style>
@import './css/reset.css';
@import './css/style.css';
</style>

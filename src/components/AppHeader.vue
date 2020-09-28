<template>
	<header id="header" :class="{ on: getScrollFlag }">
		<section class="inner">
			<h1 class="logo">
				<a href="/">
					<div class="sprite_insta_icon"></div>
					<div class="sprite_write_logo"></div>
				</a>
			</h1>
			<div class="search_box">
				<input type="text" placeholder="검색" id="search_field" />
				<div class="fake_field">
					<span class="sprite_small_search_icon"></span>
					<span>검색</span>
				</div>
			</div>
			<div class="right_icons">
				<div class="sprite_camera_icon"></div>
				<div class="sprite_compass_icon"></div>
				<div class="sprite_heart_icon_outline"></div>
				<div class="sprite_user_icon_outline"></div>
			</div>
		</section>
	</header>
</template>

<script>
import { mapMutations, mapGetters } from 'vuex';
export default {
	created() {
		window.addEventListener('scroll', this.scrollFunc);
	},
	computed: {
		...mapGetters(['getScrollFlag']),
	},
	methods: {
		...mapMutations(['setScrollFlag']),
		scrollFunc() {
			this.setScrollFlag(pageYOffset >= 10);
		},
	},
};
</script>

<style></style>

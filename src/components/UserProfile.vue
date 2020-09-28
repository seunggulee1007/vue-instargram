<template>
	<header class="top">
		<div class="user_container">
			<div class="profile_img">
				<img :src="userProfile.imgSrc" alt="프로필 이미지" />
			</div>
			<div class="user_name">
				<div class="nick_name m_text">{{ userProfile.id }}</div>
				<div class="country s_text">{{ userProfile.coutry }}</div>
			</div>
		</div>
		<div class="sprite_more_icon" :class="{ on: toggleMore }" @click="toggleMore = !toggleMore">
			<ul class="toggle_box">
				<li><button type="button">팔로우</button></li>
				<li>수정</li>
				<li>삭제</li>
			</ul>
		</div>
	</header>
</template>

<script>
export default {
	props: ['userProfile'],
	data() {
		return {
			toggleMore: false,
		};
	},
};
</script>

<style></style>

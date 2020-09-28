<template>
	<div class="side_box" :class="{ on: getScrollFlag }" ref="side_box">
		<div class="user_profile">
			<div class="profile_thumb">
				<img src="../images/thumb.jpeg" alt="프로필사진" />
			</div>
			<div class="detail">
				<div class="id m_text">KindTiger</div>
				<div class="ko_name">심선범</div>
			</div>
		</div>
		<article class="story">
			<header class="story_header">
				<div>스토리</div>
				<div class="more">모두보기</div>
			</header>

			<div class="scroll_inner">
				<div class="thumb_user">
					<div class="profile_thumb">
						<img src="../images/thumb02.jpg" alt="프로필사진" />
					</div>
					<div class="detail">
						<div class="id">King_tigerrrr</div>
						<div class="time">1시간전</div>
					</div>
				</div>
			</div>
		</article>
		<article class="recomment">
			<header class="reco_header">
				<div>회원님을 위한 추천</div>
				<div class="more">모두보기</div>
			</header>
		</article>
	</div>
</template>

<script>
import { mapGetters } from 'vuex';

export default {
	computed: {
		...mapGetters(['getScrollFlag']),
	},
	watch: {
		getScrollFlag(value) {
			if (value) {
				let calcwidth = window.innerWidth / 2 + 167;
				this.$refs.side_box.style.left = calcwidth + 'px';
			} else {
				this.$refs.side_box.removeAttribute('style');
			}
		},
	},
};
</script>

<style></style>

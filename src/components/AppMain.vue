<template>
	<section id="main_container">
		<div class="inner">
			<div class="contents_box" v-for="item in boardList" :key="item.id">
				<article class="contents" ref="contents">
					<user-profile :userProfile="item.userProfile"></user-profile>

					<div class="img_section">
						<div class="trans_inner">
							<div><img :src="item.boardImgSrc" alt="" /></div>
						</div>
					</div>

					<div class="bottom_icons">
						<div class="left_icons">
							<div class="heart_btn">
								<div
									class="sprite_heart_icon_outline"
									:class="{ on: item.heartFlag }"
									@click="chgHeart(item)"
								></div>
							</div>
							<div class="sprite_bubble_icon"></div>
							<div class="sprite_share_icon"></div>
						</div>
						<div class="right_icon">
							<div class="sprite_bookmark_outline"></div>
						</div>
					</div>

					<div class="likes">
						좋아요
						<span class="count m_text">{{ item.likeCnt }}개</span>
					</div>

					<app-comment
						v-for="comment in item.commentList"
						:key="comment.commentId"
						:comment="comment"
					></app-comment>

					<div class="timer">{{ item.timeAgo }}</div>

					<div class="comment_field">
						<input type="text" placeholder="댓글달기..." />
						<div class="upload_btn m_text">게시</div>
					</div>
				</article>
			</div>
			<app-side></app-side>
		</div>
	</section>
</template>

<script>
import AppComment from '@/components/AppComment.vue';
import AppSide from '@/components/AppSide.vue';
import UserProfile from '@/components/UserProfile.vue';

export default {
	created() {
		window.addEventListener('resize', this.resizeFunc);
	},
	components: {
		AppComment,
		AppSide,
		UserProfile,
	},
	data() {
		return {
			heartFlag: false,
			boardList: [
				{
					id: 1,
					userProfile: { id: 'KingTiger', coutry: 'Seoul, South Korea', imgSrc: '/img/thumb.7fe92ff9.jpeg' },
					likeCnt: 2324,
					heartFlag: false,
					boardImgSrc: '../images/img_section/img01.jpg',
					contents: '넘나 귀여운 강아지에요~',
					timeAgo: '1시간전',
					commentList: [
						{
							commentId: 1,
							id: 'dongdong2',
							name: '동동이',
							comment: '강아지가 너무 귀여워요',
							likeFlag: false,
						},
						{
							commentId: 2,
							id: 'leesg6107',
							name: '구승이',
							comment: '아이가 몇 살인가요 ??',
							likeFlag: true,
						},
					],
				},
				{
					id: 2,
					userProfile: { id: 'Leesg', coutry: 'Seoul, South Korea', imgSrc: '/img/thumb.7fe92ff9.jpeg' },
					likeCnt: 2324,
					heartFlag: true,
					boardImgSrc: '/img/img02.24ae2158.jpg',
					contents: '넘나 귀여운 강아지에요~',
					timeAgo: '1시간전',
					commentList: [
						{
							commentId: 1,
							id: 'digig33512',
							name: '동동이',
							comment: '고양이랑 개 인가요?',
							likeFlag: true,
						},
						{
							commentId: 2,
							id: 'leesg6107',
							name: '구승이',
							comment: '아니 개랑 고양이가 저렇게 친해도 되는 건가요? ㅋㅋㅋㅋ',
							likeFlag: true,
						},
					],
				},
			],
		};
	},
	methods: {
		chgHeart(item) {
			item.heartFlag = !item.heartFlag;
		},
		resizeFunc() {
			if (matchMedia('screen and (max-width : 800px').matches) {
				for (let width of this.$refs.contents) {
					width.style.width = window.innerWidth - 20 + 'px';
				}
			} else {
				for (let width of this.$refs.contents) {
					width.removeAttribute('style');
				}
			}
		},
	},
};
</script>

<style></style>

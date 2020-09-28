<template>
	<div class="comment_container">
		<div class="comment">
			<div class="comment-detail">
				<div class="nick_name">{{ comment.id }}</div>
				<div>{{ comment.comment }} <button type="button">삭제</button></div>
			</div>
		</div>
		<div class="small_heart">
			<div
				class="sprint_small_heart_icon_outline"
				:class="{ on: comment.likeFlag }"
				@click="chgFlag(comment)"
			></div>
		</div>
	</div>
</template>

<script>
export default {
	props: ['comment'],
	methods: {
		chgFlag(item) {
			item.likeFlag = !item.likeFlag;
		},
	},
};
</script>

<style></style>

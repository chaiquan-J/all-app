<template>
	<div class="start">
		<div class="start_body">
			<div class="bg_color"></div>
			<div class="cont_box">
				<div class="text">知道你在改变</div>
				<div class="logo"><img src="../assets/icon/logo.svg" alt="" /></div>
				<div class="title">ALL</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {};
	},
	methods: {
		goGuidance() {
			setTimeout(() => {
				this.$router.push('guidance');
			}, 1500);
		}
	},
	mounted() {
		this.goGuidance();
	}
};
</script>

<style lang="less" scoped>
.start {
	height: 100%;
	width: 100%;
	// background-color: #f9fafb;

	.start_body {
		height: 100%;
		width: 100%;
		// background-color: #f9fafb;
		display: flex;
		align-items: center;

		.bg_color {
			max-width: 750px; //按一倍图适配
			overflow: hidden;
			height: 100%;
			position: absolute;
			left: 0px;
			width: 100%;
			top: 50%;
			transform: translateY(-50%);
			background-color: #f9fafb;
		}

		.cont_box {
			height: auto;
			width: 100%;
			position: relative;
			top: 319px;

			.text {
				height: 348px;
				width: 30px;
				font-family: 'PingFangSC-Regular';
				font-size: 36px;
				color: #111a34;
				letter-spacing: 0;
				line-height: 58px;
				margin: 0 auto;
			}

			.logo {
				height: 120px;
				width: 120px;
				border-radius: 13px;
				margin: 0 auto;
				margin-top: 244px;

				img {
					height: 100%;
					width: 100%;
				}
			}

			.title {
				height: 50px;
				width: 66px;
				font-family: 'PingFangSC-Regular';
				font-size: 36px;
				color: #111a34;
				letter-spacing: 0;
				margin: 0 auto;
				margin-top: 91px;
			}
		}
	}
}
</style>

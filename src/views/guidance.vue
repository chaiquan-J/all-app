<template>
	<div class="guidance">
		<div class="guidance_body">
			<div class="bg_color"></div>
			<div class="dialogue_box">
				<div class="spirit"><img src="../assets/icon/spirit.png" alt="" /></div>
				<div class="dialogue">
					<span v-if="dialogueflg">{{ dialoguetext[0] }}</span>
					<span v-else>{{ dialoguetext[1] }}</span>
				</div>
			</div>
			<template v-if="optionflg">
				<div class="profession_btn">
					<template v-for="(item, index) in profession">
						<div class="btn" :key="index">{{ item }}</div>
					</template>
				</div>
			</template>
			<template v-else>
				<div class="purpose_btn">
					<template v-for="(item, index) in purpose">
						<div class="btn" :key="index">{{ item }}</div>
					</template>
				</div>
			</template>
			<div class="study_btn"><van-button class="btn" hairline round type="default" @click="changeOpt">确定</van-button></div>
		</div>
	</div>
</template>

<script>
import { Toast } from 'vant';
export default {
	data() {
		return {
			profession: ['大学生', '上班族', '自由派', '初中生', '高中生', '小学及学前班'],
			purpose: ['日常对话', '练发音', '出国旅游', '付费速练成课', '考雅思', '小学及学前班', '外阅读', '四六级', '考研英语'],
			optionflg: true,
			dialogueflg: true,
			dialoguetext: ['为了更好地推荐课程，请选择你的职业', '请问学习英语的目的是？（多选）']
		};
	},
	methods: {
		changeOpt() {
			if (this.dialogueflg && this.optionflg) {
				Toast.loading({
					message: '加载中...',
					forbidClick: true,
					duration: 300
				});
				this.dialogueflg = false;
				this.optionflg = false;
			} else {
				Toast.loading({
					message: '加载中...',
					forbidClick: true,
					duration: 200
				});
				this.$router.push('guidancevoice');
			}
		}
	}
};
</script>

<style lang="less" scoped>
.guidance {
	height: 100%;
	width: 100%;
	// background-color: #f9fafb;

	.guidance_body {
		height: 100%;
		width: 100%;
		// background-color: #f9fafb;
		// position: relative;

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

		.dialogue_box {
			height: auto;
			width: auto;
			margin-left: 51px;
			position: relative;
			top: 279px;

			.spirit {
				height: 64px;
				width: 80px;
				
				img {
					height: 100%;
					width: 100%;
				}
			}

			.dialogue {
				height: 93px;
				width: 563px;
				border-radius: 8px;
				box-shadow: 0px 0px 1.5px #e2e4ea;
				display: flex;
				align-items: center;
				justify-content: center;
				font-family: 'PingFangSC-Regular';
				font-size: 26px;
				color: #41485d;
				margin-top: 52px;
			}
		}

		.profession_btn {
			width: 663px;
			height: 175px;
			margin: 0 auto;
			position: absolute;
			bottom: 131px;
			left: 0;
			right: 0;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;
			align-content: space-between;

			.btn {
				height: 69px;
				width: 193px;
				border-radius: 53px;
				background-color: #f9fafb;
				box-shadow: 0px 0px 1.5px #e2e4ea;
				line-height: 69px;
				color: #41485d;
				font-family: 'PingFangSC-Regular';
				font-size: 26px;
			}
		}

		.purpose_btn {
			width: 663px;
			height: 287px;
			// background-color: #eee;
			margin: 0 auto;
			position: absolute;
			bottom: 122px;
			left: 0;
			right: 0;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;
			align-content: space-between;

			.btn {
				height: 69px;
				width: 193px;
				border-radius: 53px;
				background-color: #f9fafb;
				box-shadow: 0px 0px 1.5px #e2e4ea;
				line-height: 69px;
				color: #41485d;
				font-family: 'PingFangSC-Regular';
				font-size: 26px;
			}
		}

		.study_btn {
			height: 73px;
			width: 482px;
			margin: 0 auto;
			position: absolute;
			bottom: 21px;
			left: 0;
			right: 0;

			.btn {
				height: 100%;
				width: 100%;
				border-radius: 53px;
				background-color: #0079fe00;
				border-color: #e2e4ea;
				color: #41485d;
				font-family: 'PingFangSC-Regular';
				font-size: 26px;
			}
		}
	}
}
</style>

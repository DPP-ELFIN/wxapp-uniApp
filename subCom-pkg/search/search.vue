<template>
	<view class="search">
		<view class="search_box">
			<u-search placeholder="搜索" v-model="keyword"></u-search>
		</view>

		<view class="history" v-if="historyList.length !== 0">
			<view class="his_title">
				<text>搜索历史</text>
				<u-icon name="trash" size="24"></u-icon>
			</view>
			<view class="his_list">
				<uni-tag :text="item" v-for="(item, i) in historyList" :key="i"></uni-tag>
			</view>
		</view>

		<view class="hot" v-if="hotList.length !== 0">
			<view class="hot_title">
				<text>热门推荐</text>
			</view>
			<view class="hot_list">
				<uni-tag :text="item" v-for="(item, i) in hotList" :key="i"></uni-tag>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			keyword: '',
			historyList: ['大屁屁', '香喷喷', '香喷喷', '香喷喷', '香喷喷', '大屁屁', '香喷喷', '香喷喷', '香喷喷', '香喷喷', '大屁屁', '香喷喷', '香喷喷', '香喷喷', '香喷喷'],
			hotList: ['大屁屁', '香喷喷', '香喷喷', '香喷喷', '香喷喷', '大屁屁', '香喷喷', '香喷喷', '香喷喷', '香喷喷', '大屁屁', '香喷喷', '香喷喷', '香喷喷', '香喷喷'],
		};
	}
}
</script>

<style lang="scss" scoped>
.search {
	padding: 20rpx;

	.search_box {}

	.history {
		padding-top: 0 10rpx 50rpx;

		.his_title {
			display: flex;
			justify-content: space-between;
			align-items: center;
			height: 40px;
			font-weight: bold;
			font-size: 16px;
		}

		.his_list {
			display: flex;
			flex-wrap: wrap;

			::v-deep uni-tag {
				margin-top: 5px;
				margin-right: 5px;
				border-radius: 25rpx;
			}
		}

	}

	.hot {
		padding-top: 0 10rpx 50rpx;

		.hot_title {
			display: flex;
			justify-content: space-between;
			align-items: center;
			height: 40px;
			font-weight: bold;
			font-size: 16px;
		}

		.hot_list {
			display: flex;
			flex-wrap: wrap;

			::v-deep uni-tag {
				margin-top: 5px;
				margin-right: 5px;
				border-radius: 25rpx;
			}
		}

	}
}
</style>

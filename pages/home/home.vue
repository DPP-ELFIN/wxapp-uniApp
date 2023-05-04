<template>
	<view>

		<search></search>
		<u-tabs :list="list" @change="change" activeStyle="#02d199" :current="key"></u-tabs>
		<view class="bottom_line"> </view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			list: [
				{ key: '', name: '首页', },
				{ key: 'ask', name: '提问', },
				{ key: 'share', name: '分享', },
				{ key: '', name: '讨论', },
				{ key: '', name: '建议', },
				{ key: '', name: '公告', },
				{ key: '', name: '动态', },
			]
		}
	},
	methods: {
		change(item) {
			console.log('item', item);
		}
	}
}
</script>

<style scoped lang="scss"></style>

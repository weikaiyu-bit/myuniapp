<template>
	<view>
		<uni-grid :column="column" >
			<uni-grid-item v-for="(c,index) in data.length" :key="index">
				<view  :style="{'background-color':data[c-1].backgroundColor,color:'#D8D8D8','height': '100%','width':'100%',position: 'relative'}">
				<text class="text">
					<span :style="{'fontSize': '13px'}">{{data[c-1].number}}</span>
				<span :style="{'fontSize': '8px',paddingLeft:'3px'}">{{data[c-1].text}}</span>
				<div style="clear:both"></div>
				</text>
				<div style="position:absolute;right:0 ;bottom:0; ">
					  <icon type="success" size="15"/>
				</div>
				</view>
			</uni-grid-item>
		</uni-grid>
	</view>
</template>

<script>
	import uniGrid from "@/components/uni-grid/uni-grid.vue"
	import uniGridItem from "@/components/uni-grid-item/uni-grid-item.vue"
	export default {
		props: {
			column: {
				type: Number || String,
				default: 3
			},
			// backgroundColor:{
			// 	type:String,
			// 	default:'blue'
			// },
			data:{
				type: Array ,
				default: ['1','2','3','4','5','6']
			}
		},
		components: {
			uniGrid,
			uniGridItem
		},
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style>
.container{
	height: 100%;
	background-color: #4a10c8;
	width: 100%;
}	

/**
 * 溢出行截取
 * -o-text-overflow: ellipsis;    Opera 9-10 
 * text-overflow: ellipsis;  文本溢出时,显示省略号 IE, WebKit (Safari, Chrome), Firefox 7, Opera 11
 */

.text{
	width: 100%;  /* IE6 needs any width */
	white-space: nowrap;  /*强制不换行*/
	overflow: hidden; /*内容超出,隐藏元素 */
	}
</style>

<template>
    <div id="app" class="container pad">
		<div class="message" >
			<p>
				请在<span>12/10 16:40</span>之前完成支付，否则合同将自动关闭
			</p>
		</div>
		<div class="time bg bor-bootom tet-cen">
			<p>支付剩余时间</p>
			<p>19:48</p>
		</div>
		<div class="item bor-bootom bg">
			<span class="item-title">支付价格</span>
			<span class="item-content">￥886678</span>
		</div>
		
		<div class="orderDetai">
			<div class="item bor-bootom">
				<span class="item-title">选择支付方式</span>
			</div>
			<div class="items">
				<span class="item-title">
					<i class="addrIcon wxIcon" style="background-size: 100%;"></i>
					<div class="username">
						<p>微信</p>
						<p>微信安全支付</p>
					</div>
				</span>
				<span class="item-content">
					<i class="addrIcon chooseIcon"></i>
				</span>
			</div>
		</div>
		<footer>
		  <button @click="order" class="btn">立即支付</button>
		</footer>
    </div>
</template>

<script>
import setHtmlFont from '../../assets/commoneJs/gethtmlwidth.js';
setHtmlFont();
export default {
  name: 'app',
	methods:{
		order(){
			window.location.href = 'index.html';
		}
			
	}
}
</script>

<style lang="scss" style="text/scss">
	@import '../../assets/common.scss';
	.message {
		height: pxtorem(38);
		line-height: pxtorem(38);
		background:rgba(254,101,106,0.1);
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		p{
			padding: 0 pxtorem(10);
			span {
				color: #FE656A;
			}
		}
	}
	.bg {
		background: #fff;
		padding: 0 pxtorem(10);
	}
	.pad {
		padding-bottom: pxtorem(50);
	}
	.username {
		font-size: pxtorem(16);
		display: inline-block;
		vertical-align: top;
		p:first-child {
			font-weight: 500;
		}
		p:last-child {
			font-size: pxtorem(14);
			color:#999;
			margin: pxtorem(5) 0;
		}
	}
	.bor-bootom {
		border-bottom: 2px solid #F1F3F4;
	}
	.orderDetai {
		margin-top: pxtorem(4);
		background: #fff;
		padding: 0 pxtorem(10);
	}
	.item {
		height: pxtorem(48);
		line-height: pxtorem(48);
		font-size: 0;
		.item-title{
			display: inline-block;
			text-align: left;
			font-size: pxtorem(14);
			color:$normal-color;
			width: 50%;
		}
		.item-content{
			display: inline-block;
			text-align: right;
			font-size: pxtorem(14);
			width: 50%;
		}
	}
	.items {
		font-size: 0;
		.item-title{
			display: inline-block;
			text-align: left;
			font-size: pxtorem(14);
			color:$normal-color;
			width: 50%;
			vertical-align: middle;
		}
		.item-content{
			display: inline-block;
			text-align: right;
			font-size: pxtorem(14);
			width: 50%;
			vertical-align: middle;
		}
	}
	.item-price {
			width: 100%;
			text-align: right;
			font-size: pxtorem(16);
			display: inline-block;
	}
	.addrIcon {
		width: pxtorem(20);
		height: pxtorem(20);
		display: inline-block;
		background-size: 100%;
		vertical-align: middle;
		margin-right: pxtorem(10);
	}
	.wxIcon {
		width: pxtorem(40);
		height: pxtorem(40);
		background-size: 100% 100%;
		background: url(../../assets/images/wxIcon.png) no-repeat center center ;
	}
	.chooseIcon {
		background: url(../../assets/images/chhoseIcon.png) no-repeat center center ;
	}
	.username {
		font-size: pxtorem(16);
		display: inline-block;
		vertical-align: middle;
		p:first-child {
			font-weight: 500;
		}
		p:last-child {
			font-size: pxtorem(14);
			color:#999;
			margin: pxtorem(5) 0;
		}
	}
	.time {
		height: pxtorem(136);
		p:first-child{
			margin-top: pxtorem(60);
			font-size: pxtorem(18);
			color: #999;
		}
		p:last-child{
			margin-top: pxtorem(5);
			font-size: pxtorem(20);
			color: #333;
			font-weight: bolder;
		}
	}
</style>

<template>
    <div id="app" class="container pad">
		<div class="grounp tet-cen bg">详情</div>
		<div class="items">
			<div class="item-img">
				 <img src="../../assets/images/touxiang.jpeg" alt="user">
			</div>
			<div class="item-content">
				<p class="content-name">
					<span>李秀金</span>
				</p>
				<p>
					<span>月嫂</span>
					<span class="content-price">￥16800</span>
				</p>
			</div>
			
		</div>
		<div class="orderDetai">
			<div class="item bor-bootom">
				<span class="item-title">费用</span>
			</div>
			<div class="item bor-bootom bg">
				<span class="item-title">定金@</span>
				<span class="item-content">￥8878</span>
			</div>
			<div class="item bg">
				<span class="item-price">实付款：<i>￥8878</i></span>
			</div>
		</div>
		
		<div class="orderDetai">
			<div class="item bor-bootom">
				<span class="item-title">签约人信息</span>
			</div>
			<div class="item">
				<span class="item-title">姓名</span>
				<span class="item-content">老铁</span>
			</div>
			<div class="item">
				<span class="item-title">证件号</span>
				<span class="item-content">2121212121212121</span>
			</div>
			<div class="item">
				<span class="item-title">电话号码</span>
				<span class="item-content">121878271827182</span>
			</div>
			<div class="item">
				<span class="item-title">服务地址</span>
				<span class="item-content">北京市海淀区万寿路紫荆花孵化园</span>
			</div>
		</div>
		<div class="foot">
			<p><button @click="gotopay">确认合同</button></p>
			<p>
				您授权我们对您本人信息(包括但不限于姓名和身份证号码) 对正在签署的合同进行数字签名
			</p>
		</div>
		
    </div>
</template>

<script>
import setHtmlFont from '../../assets/commoneJs/gethtmlwidth.js';
setHtmlFont();
export default {
  name: 'app',
	methods:{
		gotopay(){
			window.location.href = 'pay.html';
		}
	}
}
</script>

<style lang="scss" style="text/scss">
	@import '../../assets/common.scss';
	.itemCtai {
		background-color: $bg;
		padding: pxtorem(4) pxtorem(10);
	}
	.items {
		background-color: #fff;
		padding: pxtorem(10);
		font-size: 0px;
		.item-img,.item-content {
			display: inline-block;
			vertical-align: top;
		}
	}
	.item-img {
		width: 25%;
		img {
			width: pxtorem(66);
			height: pxtorem(66);
			border-radius: pxtorem(4);
		}
	}
	.item-content {
		font-size: pxtorem(12);
		width: 75%;
		p {
			margin-bottom: pxtorem(12)
		}
		.content-name{
			font-size: pxtorem(16);
			font-weight: 400;
		}
		.content-price {
			float: right;
		}
	}
	.grounp {
		border-bottom: 1px solid #EBEBEB;
		height: pxtorem(48);
		line-height: pxtorem(48);
	}
	.bg {
		background: #fff;
		padding: 0 pxtorem(10);
	}
	.pad {
		padding-bottom: pxtorem(50);
	}
	.addrIcon {
			width: pxtorem(20);
			height: pxtorem(20);
			display: inline-block;
			background: url(../../assets/images/address.png) no-repeat center center ;
			background-size: 100%;
			vertical-align: pxtorem(-5);
			margin-right: pxtorem(10);
		}
	.waterOrder {
		font-size: pxtorem(16);
		color:#e4393c;
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
		border-bottom: 1px solid #EBEBEB;
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
			width: 20%;
		}
		.item-content{
			display: inline-block;
			text-align: right;
			font-size: pxtorem(14);
			width: 80%;
		}
	}
	.item-price {
			width: 100%;
			text-align: right;
			font-size: pxtorem(16);
			display: inline-block;
	}
	.foot {
		padding: pxtorem(20);
		p{
			font-size: pxtorem(14);
			color:#999;
			margin: pxtorem(4) 0;
			button{
				width: 100%;
				background:rgba(245,166,35,1);
				box-shadow:0px 2px 3px 0px rgba(255,131,14,0.5);
				border-radius:4px; 
				height: pxtorem(44);
				line-height: pxtorem(44);
				color: #fff;
				font-size: pxtorem(18);
				border:none;
				display: block;
				margin: pxtorem(10) auto auto auto;
			}
		}
	}
</style>

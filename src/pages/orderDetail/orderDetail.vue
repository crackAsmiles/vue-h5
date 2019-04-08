<template>
    <div id="app" class="container pad">
				<div class="grounp tet-cen bg">订单详情</div>
				
				<div class="bg item">
					<i class="addrIcon"></i>
					<span class="waterOrder">待签约</span>
				</div>
				<div class="bg">
					<i class="addrIcon"></i>
					<div class="username">
						<p>郭 18565668946</p>
						<p>北京市紫荆花孵化园</p>
					</div>
				</div>
				
				<div>分割线</div>
				<div class="orderDetai">
					<div class="item">
						<span class="item-title">预产期</span>
						<span class="item-content">2019-04-08</span>
					</div>
					<div class="item">
						<span class="item-title">宝宝数量</span>
						<span class="item-content">单胞胎</span>
					</div>
					<div class="item">
						<span class="item-title">服务项目</span>
						<span class="item-content">月嫂(26天)</span>
					</div>
					<div class="item">
						<span class="item-title">服务人员</span>
						<span class="item-content">李秀珍</span>
					</div>
					<div class="item bor-bootom">
						<span class="item-title">阿姨工资</span>
						<span class="item-content">￥167777</span>
					</div>
					<div class="item">
						<span class="item-title">订单编号</span>
						<span class="item-content">201904031234567</span>
					</div>
					<div class="item">
						<span class="item-title">下单时间</span>
						<span class="item-content">2019-04-03</span>
					</div>
				</div>
				
				<div class="item bor-bootom bg">
					<span class="item-title">定金@</span>
					<span class="item-content">￥8878</span>
				</div>
				<div class="item bg">
					<span class="item-price">实付款：<i>￥8878</i></span>
				</div>
				<footer>
					<div class="btn-group">
						<p><button @click="gotoSure" class="btn">取消订单</button></p>
						<p><button @click="gotoSure" class="btn">联系管家</button></p>
						<p><button @click="gotoSure" class="btn">签约</button></p>
					</div>
				</footer>
    </div>
</template>

<script>
	import setHtmlFont from '../../assets/commoneJs/gethtmlwidth.js';
	setHtmlFont();
export default {
  name: 'app',
	methods:{
		gotoSure(){
			window.location.href = 'surePact.html';
		}
	}
}
</script>

<style lang="scss" style="text/scss">
	@import '../../assets/common.scss';
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
		margin-top: pxtorem(20);
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
			font-size: pxtorem(16);
			color:$normal-color;
			width: 50%;
		}
		.item-content{
			display: inline-block;
			text-align: right;
			font-size: pxtorem(16);
			width: 50%;
		}
	}
	.item-price {
			width: 100%;
			text-align: right;
			font-size: pxtorem(16);
			display: inline-block;
	}
	.btn-group {
		display: flex;
		p{
			width: 33.33%;
		}
	}
</style>

<template>
  <div id="app" class="container">
	<ul class="nav tet-cen">
			<li @click="toggleNav(0)"><a :class="{active:active==0}">月嫂</a></li>
			<li @click="toggleNav(1)"><a :class="{active:active==1}">育婴师</a></li>
			<li @click="toggleNav(2)"><a :class="{active:active==2}">保姆</a></li>
			<li @click="toggleNav(3)"><a :class="{active:active==3}">陪护</a></li>
			<li class="tet-lt" @click="toggleRight">
				<span>筛选</span> <i class="icon choose"></i>
			</li>
	</ul>
	<!-- 筛选 -->
	<div class="bgDiv" :style="bgCss" @click="hideNav"></div>
		<div class="rightNav" :style="rightNavCss">
			<div class="chooseItem">
				<p>{{ rightNavData.serveStar.title}}</p>
				<div class="itemOption">
					<span v-for="item in rightNavData.serveStar.data" :key='item' @click="itemChoose(item,'serveStar')" :class="{itemAct: rightNavData.serveStar.status === item}">{{ item }}</span>
				</div>
			</div>
			  
			<div class="chooseItem">
				<p>{{ rightNavData.workExp.title}}</p>
				<div class="itemOption">
					<span  v-for="item in rightNavData.workExp.data" :key='item' @click="itemChoose(item,'workExp')" :class="{itemAct: rightNavData.workExp.status === item}">{{ item }}</span>
				</div>
			</div>
			<div class="chooseItem">
				<p>{{ rightNavData.age.title}}</p>
				<div class="itemOption">
					<span v-for="item in rightNavData.age.data" :key='item' @click="itemChoose(item,'age')" :class="{itemAct: rightNavData.age.status === item}">{{ item }}</span>
				</div>
			</div>
			<div class="chooseItem">
				<p>{{ rightNavData.nativePlace.title}}</p>
				<div class="itemOption">
					<span v-for="item in rightNavData.nativePlace.data" :key='item' @click="itemChoose(item,'nativePlace')" :class="{itemAct: rightNavData.nativePlace.status === item}">{{ item }}</span>
				</div>
			</div>
			<!-- <div class="chooseItem">
				<p>工作经验</p>
				<div class="itemOption">
					<span class="itemAct">1-3年</span>
					<span>3-5年</span>
					<span>5-8年</span>
					<span>8年以上</span>
				</div>
			</div>
			<div class="chooseItem">
				<p>年龄</p>
				<div class="itemOption">
					<span>20-30岁</span>
					<span>31-39岁</span>
					<span>40-49岁</span>
					<span>50岁以上</span>
				</div>
			</div>
			<div class="chooseItem">
				<p>籍贯</p>
				<div class="itemOption">
					<span>北京</span>
					<span>河北</span>
					<span>山西</span>
					<span>河南</span>
				</div>
			</div> -->
			
			<div class="chooseItemCtr">
				<span @click="reset">重置</span>
				<span @click="confirm">确定</span>
			</div>
		</div>
			
		<section class="itemCtai">
			<div class="item" @click="toDetail">
				 <div class="item-img">
					 <img src="../../assets/images/touxiang.jpeg" alt="user">
				 </div>
				 <div class="item-content">
						<p class="content-name">
							<span>张阿姨</span>
							<i class="icon glod"></i>
							<span class="content-price">￥16800</span>
						</p>
						<p class="content-intr">
							<span>3年6个月经验</span>
							<span>大专</span>
							<span>河北人</span>
							<span>42岁</span>
						</p>
						<p class="content-contr">
							特长: 擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，
						</p>
				 </div>
			</div>
			
			<div class="item">
				 <div class="item-img">
					 <img src="../../assets/images/touxiang.jpeg" alt="user">
				 </div>
				 <div class="item-content">
						<p class="content-name">
							<span>张阿姨</span>
							<i class="icon star1"></i>
							<span class="content-price">￥16800</span>
						</p>
						<p class="content-intr">
							<span>3年6个月经验</span>
							<span>大专</span>
							<span>河北人</span>
							<span>42岁</span>
						</p>
						<p class="content-contr">
							特长: 擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，
						</p>
				 </div>
			</div>
			
			<div class="item">
				 <div class="item-img">
					 <img src="../../assets/images/touxiang.jpeg" alt="user">
				 </div>
				 <div class="item-content">
						<p class="content-name">
							<span>张阿姨</span>
							<i class="icon star2"></i>
							<span class="content-price">￥16800</span>
						</p>
						<p class="content-intr">
							<span>3年6个月经验</span>
							<span>大专</span>
							<span>河北人</span>
							<span>42岁</span>
						</p>
						<p class="content-contr">
							特长: 擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，
						</p>
				 </div>
			</div>
			
			<div class="item">
				 <div class="item-img">
					 <img src="../../assets/images/touxiang.jpeg" alt="user">
				 </div>
				 <div class="item-content">
						<p class="content-name">
							<span>张阿姨</span>
							<i class="icon star3"></i>
							<span class="content-price">￥16800</span>
						</p>
						<p class="content-intr">
							<span>3年6个月经验</span>
							<span>大专</span>
							<span>河北人</span>
							<span>42岁</span>
						</p>
						<p class="content-contr">
							特长: 擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，
						</p>
				 </div>
			</div>
			
			<div class="item">
				 <div class="item-img">
					 <img src="../../assets/images/touxiang.jpeg" alt="user">
				 </div>
				 <div class="item-content">
						<p class="content-name">
							<span>张阿姨</span>
							<i class="icon star4"></i>
							<span class="content-price">￥16800</span>
						</p>
						<p class="content-intr">
							<span>3年6个月经验</span>
							<span>大专</span>
							<span>河北人</span>
							<span>42岁</span>
						</p>
						<p class="content-contr">
							特长: 擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，
						</p>
				 </div>
			</div>
			
			<div class="item">
				 <div class="item-img">
					 <img src="../../assets/images/touxiang.jpeg" alt="user">
				 </div>
				 <div class="item-content">
						<p class="content-name">
							<span>张阿姨</span>
							<i class="icon star5"></i>
							<span class="content-price">￥16800</span>
						</p>
						<p class="content-intr">
							<span>3年6个月经验</span>
							<span>大专</span>
							<span>河北人</span>
							<span>42岁</span>
						</p>
						<p class="content-contr">
							特长: 擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，擅长南北菜，面食海鲜，
						</p>
				 </div>
			</div>
			
		</section>
  </div>
</template>

<script>
import setHtmlFont from '../../assets/commoneJs/gethtmlwidth.js';
setHtmlFont();
import fastclick from 'fastclick';
fastclick.attach(document.body);
export default {
  name: 'app',
  data(){
	  return {
		  active:0,
		  rightNavCss: {
				right: "-80%",
				transition: "right .5s"
		  },
		  bgCss: {
			  display: "none",
			  transition: "display 1s"
		  },
		  rightNavData: {
			  serveStar: {
				  title: '服务星级',
				  status:'',
				  data: ['一星','二星','三星','四星','五星','金牌']
			  },
			  workExp: {
				  title: '工作经验',
				  status: '',
				  data: ['1-3年', '3-5年', '5-8年', '8年以上']
			  },
			  age: {
				  title:'年龄',
				  status: '',
				  data: ['20-30岁', '31-39岁', '40-49岁', '50岁']
			  },
			  nativePlace: {
				  title: '籍贯',
				  status: '',
				  data: ['北京', '河北', '山西', '河南']
			  }
		  }
	  }
  },
	methods:{
		toDetail(){
			window.location.href = 'detail.html';
		},
		toggleNav(num){
			this.active = num;
		},
		toggleRight(){
			this.bgCss = {
				display: "block",
				transition: "opacity 1s"
			};
			this.rightNavCss = {
				right: "0px",
				transition: "right 1s"
			};
		},
		hideNav(){
			this.bgCss = {
				display: "none",
				transition: "display 1s"
			};
			this.rightNavCss = {
				right: "-80%",
				transition: "right 1s"
			};
		},
		confirm(){
			console.log(this.rightNavData);
			this.bgCss = {
				display: "none",
				transition: "display 1s"
			};
			this.rightNavCss = {
				right: "-80%",
				transition: "right 1s"
			};
		},
		reset(){
			for(var item in this.rightNavData){
				this.rightNavData[item].status = '';
			}
		},
		itemChoose(item,str){
			this.rightNavData[str].status = item;
		}
	}
}
</script>

<style lang="scss" style="text/scss">
		@import '../../assets/common.scss';
		.icon {
			display: inline-block;
			width: pxtorem(60);
			height: pxtorem(22);
			background-size: cover;
			vertical-align: middle;
		}
		.glod {
			background-image: url(../../assets/images/金牌@2x.png);
		}
		.star1{
			background-image: url(../../assets/images/一星@2x.png);
		}
		.star2{
			background-image: url(../../assets/images/二星@2x.png);
		}
		.star3{
			background-image: url(../../assets/images/三星@2x.png);
		}
		.star4{
			background-image: url(../../assets/images/四星@2x.png);
		}
		.star5{
			background-image: url(../../assets/images/五星@2x.png);
		}
		.choose {
			background-image: url(../../assets/images/choose.png);
			width: pxtorem(13);
			height: pxtorem(14);
		}
		.nav {
			height: pxtorem(50);
			width: 100%;
			display: flex;
			display: -webkit-flex;
			flex-wrap:nowrap;
			justify-content: space-between;
			background-color: #fff;
		}
		.nav li {
			width: 20%;
			height: 100%;
			line-height: pxtorem(44);
		}
		.nav li {
			a,span {
					display: inline-block;
					border-top: pxtorem(3) solid #fff;
					border-bottom: pxtorem(3) solid #fff;
					line-height: pxtorem(44);
				}
		}
		.nav li a.active,.nav li span.active{
			color: $active-color;
			display: inline-block;
			border-bottom: pxtorem(3) solid $active-color;
			box-sizing: border-box;
		}
		.itemCtai {
			background-color: $bg;
			padding: pxtorem(4) pxtorem(10);
		}
		.item {
			background-color: #fff;
			border-radius: pxtorem(6);
			margin-bottom: pxtorem(10); 
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
				border-radius: 100%;
				margin-top: pxtorem(10);
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
			.content-intr span{
				display: inline-block;
				color: $normal-color;
				padding: 1px;
				border: 1px solid $normal-color;
				font-size: pxtorem(10);
				border-radius: pxtorem(3);
			}
			.content-contr{
				color:$middle-color;
				font-size: pxtorem(12);
				overflow: hidden;
				white-space: nowrap;
				text-overflow: ellipsis;
			}
		}
		// 筛选
		.bgDiv{
		    width: 100%;
		    height: 100%;
		    background-color: #000;
		    opacity: .5;
		    position:fixed;
		    display: none;
		    z-index: 99;
		    bottom: 0;
		}
		.rightNav{
		    width: 80%;
			padding:0 pxtorem(12);
			box-sizing: border-box;
		    max-width: 400px;
		    height: 100%;
		    background-color: #fff;
		    position: fixed;
		    z-index: 999;
		    top: 0;
		    right: -80%;
		}
	.chooseItem {
		p{
			font-size: pxtorem(14);
			font-weight: 500;
			margin: pxtorem(16) 0;
		}
		.itemOption{
			span{
				width: 32.33%;
				font-size: pxtorem(12);
				height: pxtorem(30);
				margin-bottom: pxtorem(12);
				margin-right: pxtorem(2);
				border-radius:pxtorem(3);
				border:pxtorem(1) solid rgba(229,229,229,1);
				line-height: pxtorem(30);
				text-align: center;
				display: inline-block;
				box-sizing: border-box;
			}
			span.itemAct{
				border:pxtorem(1) solid rgba(245,166,35,1);
			}
		}
	}
	.chooseItemCtr {
		height: pxtorem(46);
		border-top:pxtorem(1) solid rgba(229,229,229,1);
		font-size: 0;
		position: absolute;
		width: 100%;
		bottom: 0;
		left: 0;
		z-index: 9999;
		span {
			display: inline-block;
			font-size: pxtorem(18);
			text-align: center;
			line-height: pxtorem(46);
			font-weight: 400;
			width: 50%;
		}
		span:first-child{
			color: #333;
			border-right: pxtorem(1) solid rgba(229,229,229,1);
			box-sizing: border-box;
		}
		span:last-child{
			color: #F5A623;
		}
	}
	
		
</style>

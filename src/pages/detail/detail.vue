<template>
    <div id="app" class="container">
       <header>
		   <div class="user">
			   <div class="imgCtai">
				   <img src="../../assets/images/touxiang.jpeg" alt="">
			   </div>
			   <div class="contenCtai">
				   <p class="user-name">
					   <span>李淑芳</span>
					   <i class="icon star4"></i>
				   </p>
				   <p class="user-role">
					   <span>保姆</span>
					   <span>￥20000元/月</span>
				   </p>
			   </div>
		   </div>
		   <ul class="user-work">
			   <li>
				   <p>8年</p>
				   <p>工作经验</p>
			   </li>
			   <li>
				   <p>36岁</p>
				   <p>年龄</p>
			   </li>
			   <li>
				   <p>本科</p>
				   <p>学历</p>
			   </li>
			   <li>
				   <p>广西</p>
				   <p>籍贯</p>
			   </li>
		   </ul>
	   </header>
	   <section>
		   <div class="secCtai">
			   <ul class="toggleBar">
				   <li><a @click="toggleBar(0)" :class="{active:active==0}">工作排期</a></li>
				   <li><a @click="toggleBar(1)" :class="{active:active==1}">阿姨详情</a></li>
				   <li><a @click="toggleBar(2)" :class="{active:active==2}">服务详情</a></li>
			   </ul>
		   </div>
			 <!-- 工作排期 -->
			<div class="secCtai">
				<full-calendar :events="monthData" class="test-fc"
				  first-day='1' locale="fr"
				  @changeMonth="changeMonth"  
				  @eventClick="eventClick"    
				  @dayClick="dayClick"          
				  @moreClick="moreClick">
				</full-calendar> 
			</div>
			<!-- 分隔 -->
			<div class="segment">
				
			</div>
			
			 <!-- 阿姨详情 -->
			 <div class="secCtai">
				 
			 </div>
			 
	   </section>
	   <footer>
		   <button @click="order" class="btn">立即预约</button>
	   </footer>
    </div>
</template>

<script>
import { FullCalendar } from 'vue-fullcalendar';
import setHtmlFont from '../../assets/commoneJs/gethtmlwidth.js';
setHtmlFont();
export default {
  name: 'app',
	components: {
      'full-calendar': require('vue-fullcalendar')
  },
	data(){
		return {
			active: 0,
			monthData: [
				{
					title : '不可预约',
					start : '2019-04-01',
					end: '2019-04-15'
				},
				{
					title : '可预约',
					start : '2019-04-16',
					end: '2019-04-30'
				}
			]
		}
	},
	methods:{
		toggleBar(num){
			this.active = num;
		},
		order(){
			window.location.href = 'order.html';
		},
		changeMonth (start, end, current) {
			console.log(start)
		},
		// 点击事件
		eventClick (event, jsEvent, pos) {
			console.log('eventClick', event, jsEvent, pos)
		},
		// 点击当天
		dayClick (day, jsEvent) {
			 console.log('dayClick', day, jsEvent)
		},
		// 查看更多
		moreClick (day, events, jsEvent) {
			console.log('moreCLick', day, events, jsEvent)
		},
	}
}
</script>

<style lang="scss" type="text/scss">
	@import '../../assets/common.scss';
	header {
		padding: pxtorem(14) 0 pxtorem(30) 0;
		background: #fff;
	}
	.icon {
		display: inline-block;
		width: pxtorem(60);
		height: pxtorem(22);
		background-size: cover;
		vertical-align: bottom;
	}
	.star4 {
		background-image: url(../../assets/images/四星@2x.png);
	}
	.user {
		font-size: 0;
		margin-bottom: pxtorem(36);
	}
	.imgCtai{
		display: inline-block;
		vertical-align: top;
		img{
			width: pxtorem(80);
			height: pxtorem(80);
			border-radius: pxtorem(6);
			margin-left: pxtorem(24);
			margin-right: pxtorem(16);
		}
	} 
	.contenCtai {
		display: inline-block;
		vertical-align: top;
		.user-name{
			margin-bottom: pxtorem(14);
			span {
				font-size: pxtorem(24);
				font-weight: 400;
				color:$weight-color;
				display: inline-block;
			}
		} 
		.user-role{
			font-size: pxtorem(18);
			font-weight: 400;
			span:first-child {
				color: $weight-color;
				margin-bottom: pxtorem(8);
			}
			span:last-child {
				color: $active-color;
			}
		} 
	}
	.user-work {
		display: flex;
		display: -webkit-flex;
		flex-wrap:nowrap;
		justify-content: space-between;
	}
	.user-work li {
		width: 25%;
		text-align: center;
		p:first-child{
			font-size: pxtorem(18);
			font-weight: 500
		}
		p:last-child{
			font-size: pxtorem(12);
			color: $normal-color;
			font-weight: 400;
		}
	}
	section {
		margin-top: pxtorem(16);
		padding-bottom: pxtorem(64);
	}
	.secCtai {
		background: #fff;
		padding:0 pxtorem(10);
	}
	.toggleBar {
		display: flex;
		display: -webkit-flex;
		flex-wrap:nowrap;
		justify-content: space-between;
		height: pxtorem(50);
		line-height: pxtorem(50);
		border-bottom: 2px #E5E5E5 solid;
	}
	.toggleBar li {
		font-size: pxtorem(16);
		width: 33.33%;
		text-align: center;
		a {
			display: inline-block;
		}
		a.active{
			color: $active-color;
			background-image: url(../../assets/images/combined.png);
			background-repeat: no-repeat;
			background-position:pxtorem(5) pxtorem(44);
		}
	}
		.day-number {
				font-size: pxtorem(16) !important;
				text-align: center !important;
		}
		.event-item {
			font-size: pxtorem(10) !important;
			line-height: pxtorem(20) !important;
			height: pxtorem(20) !important;
			background-color: #fff !important;
			text-align: center !important;
			color:#C2BBC2 !important;
		}
		.full-calendar-body .weeks {
			margin: pxtorem(20) 0 !important;
			border: none !important;
		}
		.week-row {
			border: none !important;
		}
		.day-cell {
			border: none !important;
		}
		
		.segment{
			height: pxtorem(50);
			text-align: center;
			font-size: pxtorem(16);
		}
</style>

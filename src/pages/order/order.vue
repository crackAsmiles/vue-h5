<template>
    <div id="app">
		<div class="grounp tet-cen">
			确认订单
		</div>
		
		<div class="grounp">
			<div class="grounp-item">
				<label class='title' for='address'>地址</label>
				<input class="control" type="text" placeholder="地址" id="address" >
				<!-- <span class="contrIcon"></span> -->
			</div>
		</div>
		
		<div class="grounp">
			<div class="grounp-item">
				<label class='title' for='date'>预产期</label>
				<input class="control" type="text" placeholder="2019-04-05" id="date">
				<span class="contrIcon"></span>
			</div>
		</div>
		
		<div class="grounp">
			<div class="grounp-item">
				<label class='title' for='user'>服务人员</label>
				<input class="control" type="text" placeholder="李秀金" id="user">
				<!-- <span class="contrIcon"></span> -->
			</div>
		</div>
		
		<div class="grounp">
			<div class="grounp-item">
				<label class='title' for='baby'>宝宝数量</label>
				<!-- <input class="control" type="text" placeholder="请选择新生儿数量" id="baby"> -->
				<select class="control" id="baby">
					<option value="">请选择新生儿数量</option>
					<option value="1">1</option>
					<option value="2">2</option>
					<option value="3">3</option>
				</select>
				<span class="contrIcon"></span>
			</div>
		</div>
		
		<div class="grounp">
			<div class="grounp-item">
				<label class='title' for='day'>服务天数</label>
				<input class="control" type="text" placeholder="26天" id="day">
				<span class="contrIcon"></span>
			</div>
		</div>
		
		<footer>
		  <button @click="order" class="btn">立即预约</button>
		</footer>
    </div>
</template>

<script>
import setHtmlFont from '../../assets/commoneJs/gethtmlwidth.js';
setHtmlFont();
export default {
  name:'app',
  methods:{
	  order(){
		  window.location.href = 'orderDetail.html'
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
		.title,.control,.contrIcon{
			display: inline-block;
			font-size: pxtorem(15);
		}
		.grounp-item {
			font-size: 0;
			padding:0 pxtorem(12);
		}
	}
	.title {
		width: pxtorem(60);
	}
	.control {
		border: none;
		outline: none;
		padding: 4px;
		margin-left: pxtorem(10);
	}
	.contrIcon {
		float: right;
		width: pxtorem(20);
		height:pxtorem(48);
		background: url(../../assets/images/rightarrow.png) no-repeat center center;
		background-size:pxtorem(10);
	}
</style>

<template>
	<div>
		<h1>我是view1</h1>
		<a>{{userInfo.code}} - {{userInfo.count}}</a>
		<ul>
			<li v-for="(item,key) in userInfo.data">
				{{key+1}} - {{item.sex}} - {{item.classify}}
			</li>
		</ul>
	</div>
</template>
<script type="text/javascript">
import axios from 'axios'
	export default{
		name:'view1',
		data:function(){
			return {
				userInfo:{}
			}
		},
		created:function(){
			var that = this;// vue实例
			axios.get('./src/api/user.json')
			.then(function(res){
				that.userInfo = res.data;
				console.log(that.userInfo.data);
			})
			.catch(function(err){
				console.log(err);
			})
		}
	}
</script>
<style>
	
</style>
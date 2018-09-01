<template>
	<div>
		<div class="title p10">{{webName}}</div>
	</div>
</template>
<script>
export default{
	name:'webHead',
	data(){
		return {
			webName:"矿冶园"
		}
	},
};
</script>
<style type="text/css" scoped="" lang="scss">
.title {
	color: #ffffff;
	background-color: #000;
	line-height: 60px;
	text-align: center;
	font-size: 26px;
}
</style>
<template>
	<div>
		<div class="categ-course mt10">
		<p class="tc fs18">{{cateTitle.largeTitle}}</p>
		<p class="tc fs14">{{cateTitle.desc}}</p>
	</div>
	</div>
</template>
<script>
export default{
	name:'categoryTitle',
	data(){
		return {

		}
	},
	props:[
		'cateTitle',
	],
	mounted:function (argument) {

	},
	methods:{

	}
};
</script>
<style type="text/css" scoped="" lang="scss"></style>
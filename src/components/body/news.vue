<template>
	<div>
		<category-title :cateTitle="cateTitle"></category-title>
	</div>
</template>
<script>
import categoryTitle from './../head/categoryTitle'
export default{
	name:"news",
	data(){
		return {
			cateTitle:{
				largeTitle:'矿冶资讯',
				desc:"求实、求变，记录矿冶发展"
			}
		}
	},
	components:{
		categoryTitle,
	},
	mounted:function (argument) {
		// body...
	},
	methods:{

	},
};	
</script>
<style type="text/css" scoped="" lang="scss">
	
</style>
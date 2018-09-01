<template>
	<div>
		<div class="categ-course mt10">
			<category-title :cateTitle="cateTitle"></category-title>
		</div>
	</div>
</template>
<script>
import categoryTitle from './../head/categoryTitle'
export default{
	name:"classes",
	components:{
		categoryTitle,
	},
	data(){
		return {
			cateTitle:{
				largeTitle:'思维进阶',
				desc:"规整系统的学习体系，为你量身打造"
			}
		}
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
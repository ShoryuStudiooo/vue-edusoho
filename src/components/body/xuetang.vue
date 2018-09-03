<template>
	<div>
		<div class="categ-course mt10">
			<category-title :cateTitle="cateTitle"></category-title>
		</div>
		<div class="categ-title container-fluid row p20">
			<div class="btn-group col-6">
				
				<div class="btn-group">
					<button type="button" class="btn btn-success btn-sm dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
						全部课程
					</button>
					<div class="dropdown-menu">
						<a class="dropdown-item" href="#">全部课程</a>
						<a class="dropdown-item" href="#">冶金材料</a>
						<a class="dropdown-item" href="#">职业成长</a>
						<a class="dropdown-item" href="#">地址矿冶</a>
						<a class="dropdown-item" href="#">安全环保</a>
						<a class="dropdown-item" href="#">更多</a>
					</div>
				</div>
			</div>
			<div class="categ-title-status col-6">
				<div class="btn-group btn-group-sm btn-group-toggle" data-toggle="buttons">
					<label class="btn btn-secondary active">
						<input type="radio" name="options" id="option1" autocomplete="off" checked>最新
					</label>
					<label class="btn btn-secondary">
						<input type="radio" name="options" id="option2" autocomplete="off">最热
					</label>
					<label class="btn btn-secondary">
						<input type="radio" name="options" id="option3" autocomplete="off">推荐
					</label>
				</div>
			</div>
		</div>
		<div class="container-fluid">
			<div class="row">
				<a href="javascript:;" class="course-box col-6 mtb10" v-for="(item,index) in course">
					<div class="card" style="">
						<img class="card-img-top" v-bind:src="item.cover.small" v-bind:alt="item.alt">
						<div class="list-group">
							<p class="course-title p5 fs14">{{item.title}}</p>
							<div class="join_people_box list-group-item d-flex justify-content-between align-items-center">
								<div>
									<em class="join_people"></em>
									<span>{{item.studentNum}}</span>
								</div>
								<span class="badge badge-default course-free">免费</span>
							</div>
						</div>
					</div>
				</a>
			</div>
		</div>
		<div class="container text-center mtb10">
			<button class="btn btn-default btn-sm">更多课程 &gt;</button>
		</div>
	</div>
</template>

<script>
import categoryTitle from './../head/categoryTitle'

export default{
	name:'course',
	components:{
		categoryTitle,
	},
	data(){
		return {
			course:[],
			cateTitle:{
				largeTitle:'矿冶学堂',
				desc:"学堂精选行业前沿资源与科技与你共享",
			},
		}
	},
	created:function () {
		this.getData()
	},
	methods:{
		getData(){
			this.$axios({
				method:'GET',
				url:'/api/course_sets',
				params:{
					categoryId:4,
					limit:12,
					offset:0,
					sort:'-createdTime',
					type:'normal'
				},
				headers:{
					'Accept':'application/vnd.edusoho.v2+json',
				}
			}).then( res => this.course = res.data.data)
}
}
};
</script>
<style type="text/css" lang="scss" scoped >
a{
	color:#999;
}
a:hover{
	color:#000;
	transition:all 0.5s linear;
	text-decoration:none;
}
.categ-title{
	.categ-title-status{
		position:relative;
		div{
			position:absolute;
			right:0;
		}
	}
}
.course-title{
	margin-bottom:0;
	overflow:hidden;
	text-overflow:ellipsis;
	white-space:nowrap;
}
.join_people_box{
	border:none;
	padding:5px;
	.join_people{
		display:inline-block;
		height:20px;
		width:20px;
		background:url("./../../assets/images/ic_people.png") no-repeat center center / cover;
	}
	.course-free{
		color:#43bc60;
	}
	.course-red{
		color:red;
	}
}
</style>
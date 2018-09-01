<template>
  <div>
    <div id="carouselExampleControls" class="carousel slide" data-ride="carousel">
      <div class="carousel-inner">
        <div class="carousel-item" v-bind:class="{active:index==0}" v-for="(item,index) in swiperinfo">
          <img class="d-block w-100" v-bind:src="item.img" v-bind:alt="item.alt">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  name:'swiper',
  data(){
    return {
      swiperinfo:[
      {id:0,img:'./static/img/1.jpg',alt:'矿冶学堂'},
      {id:1,img:'./static/img/2.jpg',alt:'矿冶直播'},
      {id:2,img:'./static/img/3.jpg',alt:'矿冶招聘'},
      ],
    }
  },
  mounted:function () {
    this.autoPlay()
  },
  methods:{
    autoPlay:function(){
      $(".carousel").carousel({
        interval: 2000
      });
    }
  },
};
</script>

<style>
</style>
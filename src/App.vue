<template>
  <div>
    <web-head></web-head>
    <swiper></swiper>
    <xuetang></xuetang>
    <news></news>
    <classes></classes>
    <!-- <footer></footer> -->
  </div>
</template>

<script>
import webHead from '@/components/head/webhead'
import swiper from '@/components/swiper/swiper'
import xuetang from '@/components/body/xuetang'
import news from '@/components/body/news'
import classes from '@/components/body/classes'
import foot from '@/components/footer/footer'

export default {
  name: "App",
  components:{
    webHead,swiper,xuetang,news,classes,foot,
  },
  mounted: function() {
  },
  methods: {

  }
};
</script>
<style scoped>

</style>

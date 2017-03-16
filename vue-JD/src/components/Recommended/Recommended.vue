<script src="../../../../../jdDemo-dongjin-master/jdM/js/index.js"></script>
<template>
  <div class="jd_layout">
    <!--头部搜索-->
    <header class="jd_header" v-on:scroll="handleScroll">
      <div class="jd_header_box" style="background: rgba(201, 21, 35, 0);">
        <a href="#" class="icon_logo"></a>
        <div class="jd_search">
          <span class="icon_search"></span>
          <!--定义能调出搜索按钮的方式-->
          <a class="search" v-on:click="getSearch">
          </a>
        </div>
        <a href="#" class="login">登录</a>
      </div>
    </header>
    <!-- 轮播图-->
      <swiper :options="swiperOption">
        <swiper-slide><img src="./images/l1.jpg" alt=""></swiper-slide>
        <swiper-slide><img src="./images/l2.jpg" alt=""></swiper-slide>
        <swiper-slide><img src="./images/l3.jpg" alt=""></swiper-slide>
        <swiper-slide><img src="./images/l4.jpg" alt=""></swiper-slide>
        <swiper-slide><img src="./images/l5.jpg" alt=""></swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    <!--导航栏-->

    <nav class="jd_nav">
      <ul>
        <li>
          <a href="">
            <img src="./images/nav0.png" alt="">
            <p>分类查询</p>
          </a>
        </li>
        <li>
          <a href="">
            <img src="./images/nav1.png" alt="">
            <p>物流查询</p>
          </a>
        </li>
        <li>
          <a href="">
            <img src="./images/nav2.png" alt="">
            <p>购物车</p>
          </a>
        </li>
        <li>
          <a href="">
            <img src="./images/nav3.png" alt="">
            <p>我的京东</p>
          </a>
        </li>
        <li>
          <a href="">
            <img src="./images/nav4.png" alt="">
            <p>充值</p>
          </a>
        </li>
        <li>
          <a href="">
            <img src="./images/nav5.png" alt="">
            <p>领券中心</p>
          </a>
        </li>
        <li>
          <a href="">
            <img src="./images/nav6.png" alt="">
            <p>京东超市</p>
          </a>
        </li>
        <li>
          <a href="">
            <img src="./images/nav7.png" alt="">
            <p>我的关注</p>
          </a>
        </li>
      </ul>
    </nav>
    <!--秒杀-->
    <div class="title-wrap">
      <a href="" class="seckill-left-link">
        <img class="seckill-tit-img" src="https://m.360buyimg.com/mobilecms/jfs/t3451/307/73678054/7807/dd9134d/57fdff2eNb7cd186f.png">
        <div class="sk_time">
          <span class="num">{{ text0 }}</span>
          <span class="num">{{ text1 }}</span>
          <span class="str">:</span>
          <span class="num">{{ text2 }}</span>
          <span class="num">{{ text3 }}</span>
          <span class="str">:</span>
          <span class="num">{{ text4 }}</span>
          <span class="num">{{ text5 }}</span>
        </div>
      </a>
      <a class="seckill-more-link  J_ping" href="http://ms.m.jd.com/seckill/seckillList" page_name="index" report-eventlevel="1" report-eventparam="469_0_CMSSH59877_1489567261_28559_0_1_1______RIGHTCORNER_0_品质共聚放心购物_miaosha" report-eventid="MHome_BHandSeckillMore">
        品质共聚放心购物 <i class="seckill-more-icon"></i>
      </a>
    </div>
    <div class="miaosha" style="height:100px;"></div>
    <!--产品-->
    <div class="floor clearfix">
      <div class="floor-title floor-tit-img"><img class="floor-tit-bgimg" src="//st.360buyimg.com/m/images/index/floor-tit.png">
        <span class="tit-img"><img src="https://m.360buyimg.com/mobilecms/jfs/t2878/152/3484829401/8909/e1cf0ca/578de36bNae7bb54a.png!q70.jpg"> </span>
      </div>
    </div>
     <div class="floor-product-box clearfix">
        <div class="product-bot" clearfix>
          <a href="" class="p_left b_right"><img src="./images/cp1.jpg" alt=""></a>
          <a href="" class="p_right b_bottom"><img src="./images/cp2.jpg" alt=""></a>
          <a href="" class="p_right"><img src="./images/cp3.jpg" alt=""></a>
        </div>
     </div>
    <!--为您推荐-->
     <div class="floor love-floor">
      <div class="gray-text">
        <span class="gray-layout">
          <span class="gray-layout"><span class="gray-text-img"></span>为您推荐</span>
        </span>
      </div>
     </div>
      </div>


</template>

<script type="text/ecmascript-6">
  import { swiper, swiperSlide } from 'vue-awesome-swiper'
  export default {
    data() {
      return {
        timess: 7 * 60 * 60,
        swiperOption: {
          notNextTick: false,
          autoplay: 3000,
          autoplayDisableOnInteraction : false,
          loop: true,
          pagination : '.swiper-pagination'
        },
        scrolled:false
      }
    },
    mounted: function(){
       window.addEventListener('onscroll',this.handleScroll)
//      this.timerdd()
    },
    computed: {
      text0: function(){
       return  Math.floor(this.timess/(60*60))>10?Math.floor( Math.floor(this.timess/(60*60))/10):0
      },
      text1: function(){
        return  Math.floor(this.timess/(60*60))%10
      },
      text2: function(){
        return  Math.floor(this.timess/60%60)>10?Math.floor(Math.floor(this.timess/60%60)/10):0
      },
      text3: function(){
        return Math.floor(this.timess/60%60)%10
      },
      text4: function (){
        return (this.timess%60)>10?Math.floor(this.timess%60/10):0;
      },
      text5: function (){
        return this.timess%60%10
      }
    },
    methods: {
      timerdd: function () {
          var timeouts
       if(this.timess > 0){
           this.timess--
          timeouts = setTimeout(this.timerdd,1000)
       }
      },
      getSearch: function () {
        this.$parent.isSearch = true
      },
      handleScroll:function(){
        console.log('fadsfafd')
      }
    },
    components: {
      swiper,
      swiperSlide
    }
  }
</script>

<style>
  [class^="icon_"]{
    background: url("./images/sprites.png") no-repeat;
    background-size: 200px 200px;
  }

  .jd_layout{
    width:100vw;
    position:absolute;
    top:0;
    left:0;
    bottom:0;
    overflow-y:scroll;
    min-height: 100%;
    z-index:4;
  }
  /*搜索头部*/
  .jd_header{
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    height: 40px;
    z-index: 99;
  }
  /*搜索头部的内容*/
  .jd_header .jd_header_box{
    padding: 0 auto;
    position: relative;
    background: rgba(201,21,35,0);
    height: 40px;
  }
  /*logo*/
  .jd_header .jd_header_box .icon_logo{
    background-position:0 -103px;
    width: 60px;
    height: 36px;
    display: block;

    position: absolute;
    top: 4px;
    left: 10px;
  }
  .jd_header .jd_search{
    width: 100%;
    height: 40px;
    padding-left: 75px;
    padding-right: 55px;
    position: relative;
  }
  /*搜索按钮*/
  .jd_header .jd_search .icon_search{
    background-position:-60px -109px;
    width: 20px;
    height: 20px;
    display: block;
    position: absolute;
    top: 6px;
    left: 85px;
  }
  .jd_header .jd_search a.search{
    display: block;
    width: 100%;
    height: 30px;
    border-radius: 15px;
    margin-top: 5px;
    padding-left: 30px;
    background-color:#fff;
  }

  /*登录*/
  .jd_header .login{
    width: 50px;
    height: 40px;
    display: block;
    text-align: center;
    line-height: 40px;
    font-size: 15px;
    color: #fff;
    position: absolute;
    top: 0;
    right: 0;
  }

  /*轮播图*/
 .swiper-container img{
   width:100%;
 }

  /*导航栏*/
  .jd_nav{
    height: 150px;
    width: 100%;
    border-bottom: 1px solid #e0e0e0;
    padding: 0 3.125%;
    background: #fff;
    padding-top: 11px;
  }
  .jd_nav ul{
    width: 100%;
  }
  .jd_nav ul li{
    width: 25%;
    height: 69px;
    float: left;
  }
  .jd_nav ul li a{
    display: block;
    width: 100%;
    height: 100%;
    text-align: center;

  }
  .jd_nav ul li a img{
    display: block;
    width: 40px;
    height: 40px;
    margin: 0 auto;
  }
  .jd_nav ul li a p{
    font-size: 12px;
    color: #666;
    margin-top: 6px;
  }
  /*秒杀区*/
.title-wrap{
  height:34px;
  line-height: 34px;
  vertical-align: center;
}
  .seckill-left-link {
    display: inline-block;
    float: left;
    width: 68%;
  }
  .seckill-left-link    .sk_time{
    float:left;
    margin-left: 8px;
    margin-top: 8px;
  }
  .seckill-left-link .sk_time .num{
    display: block;
    width: 15px;
    height: 15px;
    text-align: center;
    background: #333;
    color:#fff;
    float:left;
    line-height: 15px;
    margin-left: 3px;
  }
  .seckill-left-link .sk_time .str{
    display: block;
    width:4px;
    height: 15px;
    text-align: center;
    float:left;
    line-height: 15px;
    margin-left:  3px;
  }
  .seckill-tit-img {
    float: left;
    display: inline-block;
    width: 69px;
    height: 27px;
    margin-top: 4px;
    margin-right: 6px;
  }

  .seckill-more-link {
    float: right;
    width: 32%;
    display: inline-block;
    color: #f23030;
    float: right;
    font-size: 10px;
    text-align: right;
    position: relative;
    padding-right: 22px;
  }
  .seckill-more-icon {
    display: inline-block;
    width: 11px;
    height: 11px;
    background: url("./images/arrow_rt.png") no-repeat;
    background-size: cover;
    position: absolute;
    right: 8px;
    top: 11px;
  }
 .title-wrap:after {
    clear: both;
    content: ".";
    height: 0;
    visibility: hidden;
    font-size: 0;
    display: block;
  }
  /*底部秒杀区*/
  .floor{
    font-size:0;
    width:100%;
  }
  .floor-title{
    position: relative;
  }
  .floor-tit-img{
    background-color:#fff;
  }
  .floor-tit-bgimg{
    position: relative;
    width: 100%;
  }
  .floor-tit-img .tit-img {
    position: absolute;
    left: 0;
    right: 0;
    top: 7px;
    bottom: 0;
    height: 73.6%;
    margin: auto;
    display: block;
    overflow: hidden;
  }
  .floor-tit-img .tit-img img {
    display: block;
    width: auto;
    max-height: 100%;
    top: 0;
    bottom: 0;
    position: absolute;
    left: 0;
    right: 0;
    text-align: center;
    margin: 0 auto;
  }

.floor-product-box{
  box-shadow: 0 0 1px 1px #e0e0e0;
  margin-top: 8px;
  background: #fff;
}
.product-bot{
  width:100%;
}
  .product-bot .p_left {
    width: 50%;
    float: left;
  }
  .product-bot .b_right {
    border-right: 1px solid #e0e0e0;
  }
  .product-bot .b_bottom {
    border-bottom: 1px solid #e0e0e0;
  }
  .product-bot .p_right {
    width: 50%;
    float: right;
  }
  .product-bot a img {
    width: 100%;
    display: block;
  }
  /*为您推荐区域*/
.love-floor{
  margin-top: 8px;
  background-color:#f0f2f5;
  overflow: hidden;
}
.gray-text{
  position:relative;
  display: -webkit-box;
  margin: 14px 5px;
  color:#848689;
  font-size: 14px;
  -webkit-box-pack:center;
}
  .gray-layout {
    padding: 0 10px;
    background-color: #f0f2f5;
    z-index: 10;
    position: relative;
    display: block;
  }
  .gray-text-img {
    background: url("./images/tuijian.png");
    background-repeat: no-repeat;
    background-size: 13px 13px;
    width: 13px;
    height: 13px;
    display: block;
    margin-right: 10px;
    position: relative;
    top: 1px;
    float: left;
  }
  .gray-text:after {
    content: "";
    height: 1px;
    width: 100%;
    position: absolute;
    top: 50%;
    left: 0;
    background-color: #cbcbcb;
    -webkit-transform: scaleY(0.5);
  }
</style>

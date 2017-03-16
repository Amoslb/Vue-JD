<template>
  <div class="sousuo">
  <header class="jd_topBar">
    <a href="javascript:void(0);" class="icon_back" v-on:click="go_back" ></a>
    <form action="">
      <input type="search" placeholder="提示"/>
    </form>
    <a href="#" class="icon_menu"></a>
  </header>
  <div class="hot-search">
    <div class="hot-search-head cf">
      <p>热门搜索</p>
      <i class="around-pic"></i>
    </div>
  </div>
  <div class="hot-search-tags">
    <span><a href="javascript:void(0);" id="searchland_hotKeywordList_0"><i>连衣裙</i></a></span>
    <span><a href="javascript:void(0);" id="searchland_hotKeywordList_0"><i>连衣裙</i></a></span>
    <span><a href="javascript:void(0);" id="searchland_hotKeywordList_0"><i>连衣裙</i></a></span>
    <span><a href="javascript:void(0);" id="searchland_hotKeywordList_0"><i>连衣裙</i></a></span>
    <span><a href="javascript:void(0);" id="searchland_hotKeywordList_0"><i>连衣裙</i></a></span>
    <span><a href="javascript:void(0);" id="searchland_hotKeywordList_0"><i>连衣裙</i></a></span>
  </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    methods: {
      go_back: function () {
        this.$parent.isSearch = false
      }
    }
  }
</script>

<style>
  .sousuo{
      width: 100%;
      position:absolute;
      min-height: 100%;
    z-index: 999;
    background: #fff;
  }
  .jd_topBar {
    height: 45px;
    width: 100%;
    background: url("./header-bg.png") repeat-x;
    background-size: 1px 44px;
    border-bottom: 1px solid #e0e0e0;
    position: absolute;
    z-index: 1000;
  }
  .jd_topBar .icon_back {
    background-position: -20px 0;
    width: 20px;
    height: 20px;
    display: block;
    margin: 12px 10px;
    position: absolute;
    top: 0;
    left: 0;
  }
  [class^="icon_"] {
    background: url("./sprites.png") no-repeat;
    background-size: 200px 200px;
  }
  .jd_topBar form {
    width: 100%;
    height: 44px;
    padding: 0 40px;
  }
  .jd_topBar form input {
    width: 100%;
    height: 32px;
    border: 1px solid #bfbfbf;
    border-radius: 4px;
    margin-top: 6px;
  }
  .jd_topBar .icon_menu {
    background-position: -60px 0;
    width: 40px;
    height: 44px;
    display: block;
    padding: 12px 10px;
    background-clip: content-box;
    background-origin: content-box;
    position: absolute;
    top: 0;
    right: 0;
  }
  i{
    font-style: normal;
    text-decoration: none;
  }
  .hot-search{
    margin-top:45px;
    padding-left: 15px;
    padding-right: 15px;
  }
  .hot-search-head{
    padding-top:3px;
  }
  .hot-search-head p{
    font-size:.875rem;
    color:#252525;
    float:left;
    width: 6.25rem;
    padding-left: 1px;
  }
  .hot-search-head i.around-pic{
    float:right;
    display: block;
    background:url(./quanquan.png);
    background-repeat: no-repeat;
    height: 17px;
    width: 22px;
  }
  .cf::after{
    content:'';
    display: block;
    height:0;
    clear:both;
    visibility: hidden;
  }
  .hot-search-tags{
    margin-top: 15px;
    padding-left:15px;
    padding-right:15px;
    text-align: center;
  }
  .hot-search-tags span{
    display: block;
    width: 33.3%;
    overflow: hidden;
    float:left;
    padding-right: 10px;
    padding-bottom: 7px;
  }
  .hot-search-tags a{
    height:1.625rem;
    line-height:  1.5rem;
    border-radius: 1.5625rem;
    display: block;
    width:100%;
    color:#848689;
    border: 1px solid #e0e0e0;
    white-space: nowrap;
    text-overflow: ellipsis;
    padding-left: 7px;
    padding-right: 7px;
    overflow: hidden;
  }
</style>

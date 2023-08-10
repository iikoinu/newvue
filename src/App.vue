<script setup>
import { ref } from 'vue';
const xialaflag = ref(false)

function mouseenter() {
  xialaflag.value = true
  console.log('----nive----')
}
function mouseleave() { xialaflag.value = false }

const xialaflagbaobei = ref(false)
function mouseentero() { xialaflagbaobei.value = true }
function mouseleaveo() { xialaflagbaobei.value = false }

const baobei = ref('宝贝')
const baobei_lie = ref(['天猫', '店铺'])
const search_downlist = ref(['西瓜', '演唱会', '彩票', '饮料'])

</script>

<template>
  <div class="one">
    <div class="one_left">
      <div class="zhong" @mouseenter=" mouseenter" @mouseleave="mouseleave">
        <span>中国大陆</span>
        <div class="zhong_xiala" v-if="xialaflag">
          <div class="zhong_lie">全球</div>
          <div class="zhong_lie">中国香港</div>
          <div class="zhong_lie">中国台湾</div>
        </div>
      </div>
      <img class="xiala" src="./ptr/下拉.png" alt="">
      <span class="qin">亲，请登录</span>
      <span class="mian">免费注册</span>
      <span class="shouji">手机逛淘宝</span>
      <span class="wang">网页无障碍</span>
    </div>
    <div class="one_right">
      <span class="wo">我的淘宝</span>
      <img class="xiala" src="./ptr/下拉.png" alt="">
      <img class="che" src="./ptr/购物车.png" alt="">
      <span class="gouwuche">购物车</span>
      <img class="shou" src="./ptr/收藏夹.png" alt="">
      <span class="shoucangjia">收藏夹</span>
      <img class="xiala" src="./ptr/下拉.png" alt="">
      <span class="shangping">商品分类</span>
      <span class="mianfei">免费开店</span>
      <span class="fenge">|</span>
      <span class="qianniu">千牛卖家中心</span>
      <img class="xiala" src="./ptr/下拉.png" alt="">
      <span class="lianxi">联系客服</span>
      <img class="xiala" src="./ptr/下拉.png" alt="">
    </div>
  </div>
  <div class="two">
    <div class="two_left">
      <img class="tao" src="./ptr/淘宝.png" alt="淘宝">
    </div>
    <div class="two_between">
      <div class="search_up">
        <div class="baobei" @mouseenter="mouseentero" @mouseleave="mouseleaveo">
          <span>{{baobei}}</span>
          <div class="baobei_xiala" v-if="xialaflagbaobei">
            <div v-for="item in baobei_lie" :key="item">{{item}}</div>
          </div>
        </div>
        <img class="xialaone" src="./ptr/下拉.png" alt="">
        <span class="fengeone">|</span>
        <input class="sousuokuang" type="text">
        <div class="sousuo">搜索</div>
      </div>
      <ul class="search_down">
        <li v-for="item in search_downlist" :key="item">{{item}}</li>
        <!-- <li>西瓜</li>
          <li>葡萄</li>
          <li>水果</li>
          <li>谷子</li> -->
        <!-- <li>rap</li> -->
      </ul>
    </div>
    <div class="two_right">
      <img class="erweima" src="./ptr/二维码.png" alt="二维码">
    </div>
  </div>
</template>

<style scoped>
.one {
  display: flex;
  justify-content: space-between;
  background-color: #f5f5f5;
  height: 30px;
}
.one_left {
  display: flex;
  align-content: center;
}
.zhong {
  position: relative;
}
.xiala {
  height: 20px;
  width: 20px;
  padding: 1px;
}
.zhong_xiala {
  background: antiquewhite;
  position: absolute;
}
.one span {
  padding: 5px;
}
.che {
  height: 15px;
  width: 15px;
}
.shou {
  height: 15px;
  width: 15px;
}
.two {
  display: flex;
  justify-content: space-between;
  background-color: #f9f6f6;
  height: 80px;
}
.twp_between {
  height: 80px;
}
.search_up {
  border: solid red;
  border-radius: 10px;
  padding: 10px;
  display: flex;
  width: 1000px;
}
.baobei {
  padding: 10px;
  position: relative;
}
.baobei_xiala {
  position: absolute;
  background: #b6e291;
}
.xialaone {
  height: 40px;
  width: 20px;
}
.fengeone {
  padding: 10px;
}
.sousuokuang {
  border: none;
  width: 825px;
}
.sousuo {
  color: #f5f5f5;
  border: red;
  border-radius: 10px;
  padding: 10px;
  background-color: red;
}
.search_down {
  display: flex;
}
.erweima {
  height: 80px;
}
ul li {
  font-size: 15px;
  list-style: none;
  margin-right: 10px;
}
</style>
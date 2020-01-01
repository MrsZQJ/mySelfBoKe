<template>
  <div id="app">
    <header>
      <div class="about">
        <div class="con">
          <ul>
            <li>
              <a href="/">Home</a>
            </li>
            <li>
              <a href="#">关于我们</a>
            </li>
          </ul>
        </div>
      </div>
      <div class="logo"></div>
    </header>
    <section class="navigation">
      <div class="con">
        <div id="bar">
          <ul>
            <li @mouseenter="moster(1)" @mouseleave="mosler(1)" @click="clk(1)">首页</li>
            <li @mouseenter="moster(2)" @mouseleave="mosler(2)" @click="clk(2)">民主</li>
            <li @mouseenter="moster(3)" @mouseleave="mosler(3)" @click="clk(3)">文明</li>
            <li @mouseenter="moster(4)" @mouseleave="mosler(4)" @click="clk(4)">和谐</li>
            <li @mouseenter="moster(5)" @mouseleave="mosler(5)" @click="clk(5)">自由</li>
          </ul>
          <div ref="mov_box" id="mov"></div>
        </div>
      </div>
      <div class="search">
        <input type="text" placeholder="请输入..." />
        <img src="../static/images/search.png" alt="search" />
      </div>
    </section>
    <div class="con">
      <router-view />
    </div>
    <footer>
      <div class="con">
        <p>没有人生来强大</p>
        <p>一切尚未可知</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      base_place: 0,
    };
  },
  methods: {
    moster(num) {
      this.$refs.mov_box.style.marginLeft = (num - 1) * 200 + "px";
    },
    mosler(num) {
      this.$refs.mov_box.style.marginLeft = this.$data.base_place + "px";
    },
    clk(num) {
      this.$data.base_place = (num - 1) * 200;
    }
  }
};
</script>

<style>
@font-face{
    font-family: 'FangZhen';
    src : url('../static/font/方正黄草_GBK.ttf');
}

* {
  padding: 0;
  margin: 0;
}
html {
  font-size: 13px;
}
body{
  background-color: #fffbf0;
}
a {
  text-decoration: none;
}
ul li {
  list-style: none;
}
.about {
  height: 30px;
  line-height: 30px;
  background-color: #f3f3f3;
}
.con {
  width: 1000px;
  margin: 0 auto;
}
.about ul {
  float: right;
}
.about ul li {
  display: inline-block;
  margin-left: 12px;
}
.about ul li a {
  color: #666;
}
.about{
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 99999;
}
.logo {
  height: 170px;
  background-image: url("../static/images/new_top-min.jpg");
  background-repeat: no-repeat;
  width: 100%;
}
.navigation {
  width: 100%;
  height: 50px;
  background-color: #bfab86;
  position: relative;
}
.search {
  position: absolute;
  right: 20px;
  width: 96px;
  height: 30px;
  border: 1px solid #fff;
  border-radius: 35px;
  display: flex;
  overflow: hidden;
  top: 9px;
  transition: 0.5s linear all;
}
.search:hover {
  width: 126px;
}
.search img {
  width: 20px;
  margin-right: 8px;
  margin-top: 5px;
  height: 20px;
}
.search input {
  flex: 1;
  height: 100%;
  width: 100%;
  background-color: rgba(0, 0, 0, 0);
  border: none;
  outline: none;
  text-indent: 1em;
  color: #fff;
}

/* 导航栏 */
#bar {
  position: relative;
}
#bar ul {
  display: flex;
}
#bar li {
  width: 200px;
  height: 50px;
  list-style: none;
  background-color: rgba(0, 0, 0, 0);
  z-index: 999999999;
  text-align: center;
  font-size: 26px;
  line-height: 50px;
  color: #f77825;
}
#mov {
  width: 202px;
  height: 50px;
  left: 0px;
  position: absolute;
  transition: all .5s linear;
  top: 0px;
  background-color: #fffbf0;
  border-top: 4px solid #f77825;
}
/* 导航栏 */

footer{
  height: 50px;
}
footer .con{
  border-top: 1px solid #666;
  text-align: center;
  padding-top: 20px;
}
footer .con p{
  line-height: 25px;
  color: #737373;
  font-size: 20px;
  font-family: "FangZhen"
}
</style>

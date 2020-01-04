<template>
  <div class="body">
    <div id="carousel" @mouseover="stopAuto" @mouseout="autoPlay">
      <div
        class="carousel-box"
        :style="{width:allCount,'-webkit-transition':transitionConfig,'-webkit-transform':slateX}"
        ref="carousel"
      >
        <div class="carousel-item" :style="{'-webkit-transform':imgLateX}" v-if="loop">
          <img :src="imgList[imgList.length-1].img" />
        </div>
        <div
          class="carousel-item"
          v-for="(item,index) in imgList"
          :style="{'-webkit-transform':getImgLateX(index)}"
          :key="index"
        >
          <img :src="item.img" />
        </div>
        <div class="carousel-item" :style="{'-webkit-transform':endImgLateX}" v-if="loop">
          <img :src="imgList[0].img" />
        </div>
      </div>
      <span class="carousel-left" @click="toLeft">&#8249;</span>
      <span class="carousel-right" @click="toRight">&#8250;</span>
      <div class="carousel-dots" v-if="dots">
        <button
          v-for="(item,index) in imgList.length"
          :key="index"
          :class="{active:index==dotsIndex}"
          @click="toDots(index)"
        >{{item}}</button>
      </div>
    </div>
    <div class="con">
      <div class="new_article">
        <h3>最新文章</h3>
        <div class="article_list">
          <img src="../../../static/images/201912242301491719_s.png" alt />
          <div class="r_con">
            <h4>
              <a href="#">圣诞节的正确打开方式</a>
            </h4>
            <p>今天是圣诞节，中西文化的融合，让孩子爱上这个神秘的圣诞爷爷。豌豆豆还小，还不知道要礼物，我感觉明年的今天，老母亲就该扮演像模像样的圣诞老人，给娃准备他喜欢的礼物，但愿他想要的礼物不要那么抽象。那这篇就说一下圣诞节的正</p>
            <p class="b_r">
              <span>
                <a href="#">韶华追忆</a>
              </span>
              <span>2019-12-24 23:01:53</span>
              <!-- <span></span> -->
            </p>
          </div>
        </div>
        <div class="article_list">
          <img src="../../../static/images/201912242301491719_s.png" alt />
          <div class="r_con">
            <h4>
              <a href="#">圣诞节的正确打开方式</a>
            </h4>
            <p>今天是圣诞节，中西文化的融合，让孩子爱上这个神秘的圣诞爷爷。豌豆豆还小，还不知道要礼物，我感觉明年的今天，老母亲就该扮演像模像样的圣诞老人，给娃准备他喜欢的礼物，但愿他想要的礼物不要那么抽象。那这篇就说一下圣诞节的正</p>
            <p class="b_r">
              <span>
                <a href="#">韶华追忆</a>
              </span>
              <span>2019-12-24 23:01:53</span>
              <!-- <span></span> -->
            </p>
          </div>
        </div>
        <div class="article_list">
          <img src="../../../static/images/201912242301491719_s.png" alt />
          <div class="r_con">
            <h4>
              <a href="#">圣诞节的正确打开方式</a>
            </h4>
            <p>今天是圣诞节，中西文化的融合，让孩子爱上这个神秘的圣诞爷爷。豌豆豆还小，还不知道要礼物，我感觉明年的今天，老母亲就该扮演像模像样的圣诞老人，给娃准备他喜欢的礼物，但愿他想要的礼物不要那么抽象。那这篇就说一下圣诞节的正</p>
            <p class="b_r">
              <span>
                <a href="#">韶华追忆</a>
              </span>
              <span>2019-12-24 23:01:53</span>
              <!-- <span></span> -->
            </p>
          </div>
        </div>
        <div class="article_list">
          <img src="../../../static/images/201912242301491719_s.png" alt />
          <div class="r_con">
            <h4>
              <a href="#">圣诞节的正确打开方式</a>
            </h4>
            <p>今天是圣诞节，中西文化的融合，让孩子爱上这个神秘的圣诞爷爷。豌豆豆还小，还不知道要礼物，我感觉明年的今天，老母亲就该扮演像模像样的圣诞老人，给娃准备他喜欢的礼物，但愿他想要的礼物不要那么抽象。那这篇就说一下圣诞节的正</p>
            <p class="b_r">
              <span>
                <a href="#">韶华追忆</a>
              </span>
              <span>2019-12-24 23:01:53</span>
              <!-- <span></span> -->
            </p>
          </div>
        </div>
        <div class="article_list">
          <img src="../../../static/images/201912242301491719_s.png" alt />
          <div class="r_con">
            <h4>
              <a href="#">圣诞节的正确打开方式</a>
            </h4>
            <p>今天是圣诞节，中西文化的融合，让孩子爱上这个神秘的圣诞爷爷。豌豆豆还小，还不知道要礼物，我感觉明年的今天，老母亲就该扮演像模像样的圣诞老人，给娃准备他喜欢的礼物，但愿他想要的礼物不要那么抽象。那这篇就说一下圣诞节的正</p>
            <p class="b_r">
              <span>
                <a href="#">韶华追忆</a>
              </span>
              <span>2019-12-24 23:01:53</span>
              <!-- <span></span> -->
            </p>
          </div>
        </div>
      </div>
      <div class="r_detail" :style="max_style">
        <div class="myself">
          <img src="../../../static/images/user_cover.jpg" alt />
          <div class="author">
            <p>
              <span>挚 梦</span>
              <span>作者</span>
            </p>
            <div>人最大的不同乃思考.</div>
          </div>
          <img src="../../../static/images/timg.png" alt class="yuan" />
        </div>
        <canvas id="canvas" style="border: 1px solid skyblue;height: 100%;"></canvas>
        <div class="local">
          <div class="l_box"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      imgList: [
        {
          img: "./static/images/b1.png"
        },
        {
          img: "./static/images/b2.png"
        },
        {
          img: "./static/images/b3.png"
        },
        {
          img: "./static/images/b4.png"
        }
      ],
      // 图片宽
      imgWidth: 750,
      // 指示器
      dots: true,
      arrow: true,
      // 初始播放位置
      initIndex: 0,
      // 是否循环
      loop: true,
      // 持续时间
      duration: 0.3,
      // 自动播放
      auto: true,
      // 自动播放时间间隔
      autoTime: 2000,
      imgIndex: 0,
      durationTime: 0.2,
      dotsIndex: 0,
      autoer: null,
      max_style: {},
      // 时间显示变量
      digit: [
        [
          [0, 0, 1, 1, 1, 0, 0],
          [0, 1, 1, 0, 1, 1, 0],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 1, 1, 0, 1, 1, 0],
          [0, 0, 1, 1, 1, 0, 0]
        ], //0
        [
          [0, 0, 0, 1, 1, 0, 0],
          [0, 1, 1, 1, 1, 0, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [1, 1, 1, 1, 1, 1, 1]
        ], //1
        [
          [0, 1, 1, 1, 1, 1, 0],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 1, 1, 0, 0, 0],
          [0, 1, 1, 0, 0, 0, 0],
          [1, 1, 0, 0, 0, 0, 0],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 1, 1, 1, 1, 1]
        ], //2
        [
          [1, 1, 1, 1, 1, 1, 1],
          [0, 0, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 1, 1, 1, 0, 0],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 1, 1, 1, 1, 1, 0]
        ], //3
        [
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 1, 1, 1, 0],
          [0, 0, 1, 1, 1, 1, 0],
          [0, 1, 1, 0, 1, 1, 0],
          [1, 1, 0, 0, 1, 1, 0],
          [1, 1, 1, 1, 1, 1, 1],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 1, 1, 1, 1]
        ], //4
        [
          [1, 1, 1, 1, 1, 1, 1],
          [1, 1, 0, 0, 0, 0, 0],
          [1, 1, 0, 0, 0, 0, 0],
          [1, 1, 1, 1, 1, 1, 0],
          [0, 0, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 1, 1, 1, 1, 1, 0]
        ], //5
        [
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 1, 1, 0, 0, 0],
          [0, 1, 1, 0, 0, 0, 0],
          [1, 1, 0, 0, 0, 0, 0],
          [1, 1, 0, 1, 1, 1, 0],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 1, 1, 1, 1, 1, 0]
        ], //6
        [
          [1, 1, 1, 1, 1, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 0, 1, 1, 0, 0, 0],
          [0, 0, 1, 1, 0, 0, 0],
          [0, 0, 1, 1, 0, 0, 0],
          [0, 0, 1, 1, 0, 0, 0]
        ], //7
        [
          [0, 1, 1, 1, 1, 1, 0],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 1, 1, 1, 1, 1, 0],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 1, 1, 1, 1, 1, 0]
        ], //8
        [
          [0, 1, 1, 1, 1, 1, 0],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [1, 1, 0, 0, 0, 1, 1],
          [0, 1, 1, 1, 0, 1, 1],
          [0, 0, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 0, 1, 1],
          [0, 0, 0, 0, 1, 1, 0],
          [0, 0, 0, 1, 1, 0, 0],
          [0, 1, 1, 0, 0, 0, 0]
        ], //9
        [
          [0, 0, 0, 0],
          [0, 0, 0, 0],
          [0, 1, 1, 0],
          [0, 1, 1, 0],
          [0, 0, 0, 0],
          [0, 0, 0, 0],
          [0, 1, 1, 0],
          [0, 1, 1, 0],
          [0, 0, 0, 0],
          [0, 0, 0, 0]
        ] //:
      ],
      RADIUS: 1.8,
      MARGIN_LEFT: 2,
      MARGIN_TOP: 30,
      colors: [
        "#33B5E5",
        "#0099CC",
        "#AA66CC",
        "#9933CC",
        "#99CC00",
        "#669900",
        "#FFBB33",
        "#FF8800",
        "#FF4444",
        "#CC0000"
      ],
      balls: [],
      currentTime: NaN,
      WINDOW_WIDTH: 310,
      WINDOW_HEIGHT: 130,
      ctx: NaN,
      // 时间显示变量
    };
  },
  computed: {
    allCount() {
      return this.imgList.length * this.imgWidth + "px";
    },
    slateX() {
      return "translate3d(" + -this.imgIndex * this.imgWidth + "px,0,0)";
    },
    transitionConfig() {
      return "all " + this.durationTime + "s";
    },
    imgLateX() {
      let width = -this.imgWidth;
      return "translate3d(" + width + "px,0,0)";
    },
    //   getImgLateX(i){
    //     let width = this.imgWidth*i
    //     return 'translate3d('+(width)+'px,0,0)'
    //   },
    endImgLateX() {
      let width = this.imgList.length;
      return "translate3d(" + width + "px,0,0)";
    }
  },
  created() {
    this.imgIndex = this.dotsIndex = this.initIndex;

    this.durationTime = this.duration;

    if (this.auto) this.autoPlay();
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
    var canvas = document.getElementById("canvas");
    canvas.width = this.WINDOW_WIDTH;
    canvas.height = this.WINDOW_HEIGHT;
    this.ctx = canvas.getContext("2d");
    this.currentTime = this.time_count();
    setInterval(() => {
      this.render(this.ctx);
      this.updata();
    }, 50);
  },
  methods: {
    updata() {
      var nowTime = this.time_count();
      var nowThour = parseInt(nowTime / 3600);
      var nowTminutes = parseInt((nowTime - nowThour * 3600) / 60);
      var nowTseconds = nowTime % 60;
      var currenthour = parseInt(this.currentTime / 3600);
      var currentminutes = parseInt((this.currentTime - currenthour * 3600) / 60);
      var currentseconds = this.currentTime % 60;
      if (nowTime != this.currentTime) {
        if (parseInt(nowThour / 10) != parseInt(currenthour / 10)) {
          this.addBalls(
            this.MARGIN_LEFT,
            this.MARGIN_TOP,
            parseInt(nowThour / 10)
          );
        }
        if (parseInt(nowThour % 10) != parseInt(currenthour % 10)) {
          this.addBalls(
            this.MARGIN_LEFT + 15 * (this.RADIUS + 1),
            this.MARGIN_TOP,
            parseInt(nowThour % 10)
          );
        }
        if (parseInt(nowTminutes / 10) != parseInt(currentminutes / 10)) {
          this.addBalls(
            this.MARGIN_LEFT + 39 * (this.RADIUS + 1),
            this.MARGIN_TOP,
            parseInt(nowTminutes / 10)
          );
        }
        if (parseInt(nowTminutes % 10) != parseInt(currentminutes % 10)) {
          this.addBalls(
            this.MARGIN_LEFT + 54 * (this.RADIUS + 1),
            this.MARGIN_TOP,
            parseInt(nowTminutes % 10)
          );
        }
        if (parseInt(nowTseconds / 10) != parseInt(currentseconds / 10)) {
          this.addBalls(
            this.MARGIN_LEFT + 78 * (this.RADIUS + 1),
            this.MARGIN_TOP,
            parseInt(nowTseconds / 10)
          );
        }
        if (parseInt(nowTseconds % 10) != parseInt(currentseconds % 10)) {
          this.addBalls(
            this.MARGIN_LEFT + 93 * (this.RADIUS + 1),
            this.MARGIN_TOP,
            parseInt(nowTseconds % 10)
          );
        }
        this.currentTime = nowTime;
      }
      this.updateBalls();
    },
    updateBalls() {
      for (var i = 0; i < this.balls.length; i++) {
        this.balls[i].x += this.balls[i].vx;
        this.balls[i].y += this.balls[i].vy;
        this.balls[i].vy += this.balls[i].g;
        if (this.balls[i].y >= this.ctx.canvas.height - this.balls[i].r) {
          this.balls[i].y = this.ctx.canvas.height - this.balls[i].r;
          this.balls[i].vy = -this.balls[i].vy * 0.6;
        }
        if (this.balls[i].x >= this.ctx.canvas.width - this.balls[i].r) {
          this.balls.splice(i, 1);
        }
        if (this.balls[i].x <= 0 + this.balls[i].r) {
          this.balls.splice(i, 1);
        }
      }
    },
    addBalls(x, y, num) {
      for (var i = 0; i < this.digit[num].length; i++) {
        for (var j = 0; j < this.digit[num][i].length; j++) {
          if (this.digit[num][i][j] == 1) {
            var aball = {
              x: x + j * 2 * (this.RADIUS + 1) + (this.RADIUS + 1),
              y: y + i * 2 * (this.RADIUS + 1) + (this.RADIUS + 1),
              r: this.RADIUS,
              g: 1.5 + Math.random(),
              vx: Math.pow(-1, Math.ceil(Math.random() * 10)) * 4,
              vy: -5,
              color: this.colors[Math.floor(Math.random() * this.colors.length)]
            };
            this.balls.push(aball);
          }
        }
      }
    },
    time_count() {
      var tim = new Date();
      var ret =
        tim.getHours() * 3600 + tim.getMinutes() * 60 + tim.getSeconds();
      return ret;
    },
    render(ctx) {
      var currentRet = this.time_count();
      var hour = 12,
        minutes = 34,
        seconds = 56;
      hour = parseInt(currentRet / 3600);
      minutes = parseInt((currentRet - hour * 3600) / 60);
      seconds = currentRet % 60;
      ctx.clearRect(0, 0, ctx.canvas.width, ctx.canvas.height);
      this.renderDigit(this.MARGIN_LEFT, this.MARGIN_TOP, parseInt(hour / 10), ctx);
      this.renderDigit(
        this.MARGIN_LEFT + 15 * (this.RADIUS + 1),
        this.MARGIN_TOP,
        parseInt(hour % 10),
        ctx
      );
      this.renderDigit(
        this.MARGIN_LEFT + 30 * (this.RADIUS + 1),
        this.MARGIN_TOP,
        10,
        ctx
      );
      this.renderDigit(
        this.MARGIN_LEFT + 39 * (this.RADIUS + 1),
        this.MARGIN_TOP,
        parseInt(minutes / 10),
        ctx
      );
      this.renderDigit(
        this.MARGIN_LEFT + 54 * (this.RADIUS + 1),
        this.MARGIN_TOP,
        parseInt(minutes % 10),
        ctx
      );
      this.renderDigit(
        this.MARGIN_LEFT + 69 * (this.RADIUS + 1),
        this.MARGIN_TOP,
        10,
        ctx
      );
      this.renderDigit(
        this.MARGIN_LEFT + 78 * (this.RADIUS + 1),
        this.MARGIN_TOP,
        parseInt(seconds / 10),
        ctx
      );
      this.renderDigit(
        this.MARGIN_LEFT + 93 * (this.RADIUS + 1),
        this.MARGIN_TOP,
        parseInt(seconds % 10),
        ctx
      );
      for (var i = 0; i < this.balls.length; i++) {
        ctx.fillStyle = this.balls[i].color;
        ctx.beginPath();
        ctx.arc(
          this.balls[i].x,
          this.balls[i].y,
          this.RADIUS,
          0,
          2 * Math.PI,
          true
        );
        ctx.closePath();
        ctx.fill();
      }
    },
    renderDigit(x, y, num,ctx) {
      this.ctx.fillStyle = "skyblue";
      for (var i = 0; i < this.digit[num].length; i++) {
        for (var j = 0; j < this.digit[num][i].length; j++) {
          if (this.digit[num][i][j] == 1) {
            this.ctx.beginPath();
            this.ctx.arc(
              x + j * 2 * (this.RADIUS + 1) + (this.RADIUS + 1),
              y + i * 2 * (this.RADIUS + 1) + (this.RADIUS + 1),
              this.RADIUS,
              0,
              2 * Math.PI
            );
            this.ctx.fill();
          }
        }
      }
    },
    // 111111111111111111

    getImgLateX(i) {
      let width = this.imgWidth * (i + 1);
      return "translate3d(" + width + "px,0,0)";
    },
    toLeft() {
      if (this.loop) {
        this.imgIndex--;
        this.dotsIndex--;
        if (this.dotsIndex <= -1) this.dotsIndex = this.imgList.length - 1;

        if (this.imgIndex <= -2) this.loopFn("left");
      } else {
        if (this.imgIndex == 0)
          return (this.dotsIndex = this.imgIndex = this.imgList.length - 1);
        this.imgIndex--;
        this.dotsIndex--;
      }
    },
    toRight() {
      if (this.loop) {
        // alert(this.loop)

        this.imgIndex++;
        this.dotsIndex++;
        if (this.dotsIndex == this.imgList.length) this.dotsIndex = 0;
        if (this.imgIndex == this.imgList.length + 1) this.loopFn("right");
      } else {
        this.imgIndex++;
        this.dotsIndex++;
        if (this.imgIndex > this.imgList.length - 1)
          return (this.dotsIndex = this.imgIndex = 0);
      }
    },
    loopFn(type) {
      const dur = this.durationTime;
      this.durationTime = 0;

      this.imgIndex = type == "right" ? 0 : this.imgList.length - 1;

      setTimeout(() => {
        this.$nextTick(function() {
          this.durationTime = dur;

          if (type == "right") this.imgIndex++;
          else this.imgIndex--;
        });
      }, 30);
    },
    toDots(index) {
      this.dotsIndex = this.imgIndex = index;
    },
    autoPlay() {
      if (this.auto) {
        clearInterval(this.autoer);
        this.autoer = setInterval(() => {
          this.toRight();
        }, this.autoTime);
      }
    },
    stopAuto() {
      if (this.auto) return clearInterval(this.autoer);
    },
    handleScroll() {
      var scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      if (scrollTop > 600) {
        this.max_style = { position: "fixed", top: "0px", right: "15%" };
      } else {
        this.max_style = { position: "relative" };
      }
    }
  }
};
</script>

<style scoped>
/* 轮播图 */
#carousel {
  position: relative;
  overflow: hidden;
  width: 100%;
  height: 400px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 5px;
}

.carousel-left,
.carousel-right {
  position: absolute;
  top: 56%;
  display: inline-block;
  transform: translateY(-50%);
  color: #fff;
  border-radius: 50%;
  text-align: center;
  cursor: pointer;
  font-size: 60px;
  border-radius: 50%;
  transition: all 0.5s;
}

.carousel-left {
  left: 0;
}

.carousel-right {
  right: 0;
}

.carousel-left:hover,
.carousel-right:hover {
  color: black;
}

.carousel-dots {
  position: absolute;
  bottom: 20px;
  text-align: center;
  left: 50%;
  transform: translateX(-50%);
}

.carousel-dots button {
  width: 17px;
  height: 17px;
  background: rgba(127, 124, 124, 0.5);
  display: inline-block;
  margin: 0 5px;
  border-radius: 50%;
  color: #000;
  border: none;
  outline: none;
  transition: all 0.2s;
  cursor: pointer;
  font-size: 7px;
}

.carousel-dots button:hover,
.carousel-dots button.active {
  background: rgba(51, 122, 183, 0.8);
  color: #fff;
}

.carousel-item {
  width: 1000px;
  position: absolute;
  top: 0;
  left: 0;
  height: 400px;
}

.carousel-item img {
  width: 100%;
  height: 100%;
}
/* 轮播图 */
.con {
  display: flex;
}
.new_article {
  width: 67%;
}
.new_article > h3 {
  font-size: 16px;
  line-height: 36px;
  border-bottom: #db6d4c 4px solid;
}
.article_list {
  padding: 30px 0px;
  border-bottom: #bfab86 1px solid;
  display: flex;
  transition: all 1s;
}
.article_list:hover {
  background-color: #fff;
}
.article_list > img {
  width: 167px;
  height: 137px;
  transition: 0.3s all linear;
}
.article_list > img:hover {
  transform: scale(1.05);
}
.r_con {
  margin-left: 18px;
  flex: 1;
}
.r_con > h4 {
  font-size: 16px;
  margin-bottom: 10px;
}
.new_article a {
  color: #474645;
}
.r_con p {
  font-size: 12px;
  color: #777;
  line-height: 22px;
}
.b_r {
  margin: 10px 0;
  line-height: 20px;
}
.b_r a {
  color: #759b08;
}
.b_r span {
  padding-left: 20px;
  background-image: url("../../../static/images/mynewsbg.png");
  background-repeat: no-repeat;
  margin-right: 10px;
}
.b_r span:nth-child(1) {
  background-position: 0px 2px;
}
.b_r span:nth-child(2) {
  float: right;
  background-position: 0px -48px;
}
/* .b_r span:nth-child(3){
  background-image: url('../../../static/images/mynewsbg.png');
  float: right;
} */
.r_detail {
  margin-left: 20px;
}
.myself {
  width: 315px !important;
  height: 260px !important;
  margin-top: 35px;
  background-color: #fff;
}
.myself > img:nth-child(1) {
  width: 100%;
}
.author {
  width: 100%;
  height: 155px;
}
.author p {
  font-size: 16px;
  text-align: center;
  margin-top: 50px;
}
.author p span:nth-child(2) {
  font-size: 12px;
  color: #ff5f33;
  border: 1px solid #ff5f33;
  padding: 3px 8px;
  position: relative;
  margin-left: 8px;
}
.author p span:nth-child(2)::before {
  content: "<";
  position: absolute;
  left: -10px;
  top: 7px;
  background-color: #fff;
  line-height: 7px;
  font-size: 16px;
}
.author div {
  padding: 20px 15px 15px;
  border: 1px dashed #efefef;
  margin-top: 30px;
  font-size: 20px;
  letter-spacing: 1px;
  font-family: "FangZhen";
}
.yuan {
  width: 80px;
  height: 80px;
  border-radius: 80px;
  position: absolute;
  top: 90px;
  left: 50%;
  margin-left: -40px;
  transition: all 2s ease;
}
.yuan:hover {
  transform: rotateZ(1800deg);
}
#canvas{
  width: 100% !important;
  height: 75px !important ;
}
.local{
  width: 100%;
  margin-top: 25px;
}
.l_box{
  width: 45%;
  border: 1px solid #FFDD99;
  background-color: #FFF9ED;
}
</style>

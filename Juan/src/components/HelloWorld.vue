<template>

  <div class="back_1" @mousemove="mouseMove1">
<!--    <embed src="../assets/demo3.mp3" autostart=true loop=true>-->
<!--    <div ref="circleref1" :style="{top: styleObject}" class="centercircle">-->

    <div class="music" @click="music1">Music:On</div>

    <div class="beian">
      <a href="http://www.beian.gov.cn/">京ICP备19041410号-1</a>
      <div>© 2020 | Design By Juan</div>
    </div>

    <div class="leftIntro">
      <div class="cutoff" style="position: absolute;top:50%;left:20vw;width: 15vw;height: 1vw;background-color: #a6dadd"></div>
      <div class="title1" style="">卷毛兔</div>
      <div class="title2" style="">的个人网站</div>
      <div class="title3" style="">Juan.M.T.</div>

    </div>
    <div ref="circleref1" class="centercircle">
      <div  class="centercircle2">
        <div  class="centercircle3">
          <div ></div>
        </div>
      </div>
    </div>
    <div class="outer5" >
      <div class="studymore">
        <div class="js" style="">JavaScript</div>
        <div class="vue" style="">Vue</div>
        <div class="ae" style="">After Effect</div>
        <div class="ps" style="">PhotoShop</div>
        <div class="css" style="">Html/CSS</div>
      </div>
    </div>
    <div class="outer" name="nameouter"  :class="{'outer_2': isChange == index_is}" >
      <div class="circle_study"  @click="toIntro(index_is)" :style="style_1">
        <div style="margin-left: -20%;font-size: 3vw">个人</div>
        <div style="margin-top: -6%;margin-left: 15%;font-size: 2.5vw">简介</div>
      </div>
    </div>
    <div class="outer2" name="nameouter">
      <div class="circle_blog" @mouseenter="mouseOn1" @mouseleave="mouseLeave1" @click="toIntro(index_is)" :style="style_2" onclick="window.open('http://studynotes.juanmaotu.top/','_self')">
        <div style="margin-left: -20%;font-size: 3vw">学习</div>
        <div style="margin-top: -6%;margin-left: 15%;font-size: 2.5vw">记录 </div>
      </div>
    </div>
    <div class="outer3" name="nameouter">
      <div class="circle_works" @click="toIntro(index_is)" :style="style_3">
        <div style="margin-left: -20%;font-size: 3vw">作品</div>
        <div style="margin-top: -6%;margin-left: 15%;font-size: 2.5vw">展示</div>
      </div>
    </div>
    <div class="outer4" name="nameouter">
      <div class="circle_other" @click="toIntro(index_is)" :style="style_4">other</div>
    </div>
<!--    <video style="width: 0;height: 0;" id = "music2" src="../assets/demo3.mp3" autoplay="autoplay" loop="loop"></video>-->
    <audio id = "music2" autoplay="autoplay">
      <source src="../assets/demo3.mp3" type="audio/mpeg">
      您的浏览器不支持 audio 元素。
    </audio>
  </div>
</template>

<script>
    function sleep (time) {
        return new Promise((resolve) => setTimeout(resolve, time));
    }

    export default {
    name: 'HelloWorld',
    data () {
      return {
        index_is: 100,
        isChange :0,
        rotate1 :0,
        is: document.body.clientWidth,
        screenWidth: document.body.clientWidth,
        screenHeight: document.body.clientHeight
      }
    },
      // mounted() {
      //     setTimeout(() => {
      //         window.L2Dwidget.init({
      //             pluginRootPath: 'live2dw/',
      //             pluginJsPath: 'lib/',
      //             pluginModelPath: 'live2d-widget-model-z16/assets/',
      //             tagMode: false,
      //             debug: false,
      //             model: { jsonPath: '../live2dw/live2d-widget-model-z16/assets/z16.model.json' },
      //             display: { position: 'right', width: 100, height: 200 },
      //             mobile: { show: true },
      //             log: false
      //         })
      //     }, 1000)
      // },
      created () {
          // setTimeout(() => {
          //     window.L2Dwidget.init({
          //         pluginRootPath: 'static/live2dw/',
          //         pluginJsPath: 'lib/',
          //         pluginModelPath: 'live2d-widget-model-z16/assets/',
          //         tagMode: false,
          //         debug: false,
          //         model: { jsonPath: '../static/live2dw/live2d-widget-model-z16/assets/z16.model.json' },
          //         display: { position: 'left', width: 300, height: 1500 },
          //         mobile: { show: true },
          //         log: false
          //     })
          // }, 1000)
      },
    computed:{
        // rotate1:function(){
        //
        // },
        windowsize(){
          const {screenWidth,screenHeight}  = this;
          return{
              screenWidth,
              screenHeight
          }
        },
        styleObject:function () {
          var is2 = document.body.clientWidth;
          var is3 = document.body.clientHeight;
          var res = is3/2-is2*0.1;
          // alert(res);
          return res+'px';
        },
        style_1:function () {
            var rotate1 = -45;
            // var rotate1 = this.rotate1;
            return  `transform:rotate(${rotate1}deg)`;
        },
        style_2:function () {
            var rotate1 = -90;
            // var rotate1 = this.rotate1;
            return  `transform:rotate(${rotate1}deg)`;
        },
        style_3:function () {
            var rotate1 = -135;
            // var rotate1 = this.rotate1;
            return  `transform:rotate(${rotate1}deg)`;
        },
        style_4:function () {
            var rotate1 = -180;
            // var rotate1 = this.rotate1;
            return  `transform:rotate(${rotate1}deg)`;
        }
    },
      methods:{
        mouseMove1(){
          console.log("e.targetTouches[0].clientX ");
        },
        mouseOn1(){
            // alert("on");
            var more = document.getElementsByClassName("studymore")[0];
            more.style.opacity = 1;
            more.style.marginLeft = '-2vw';
            more.style.marginRight = '-14vw';
            more.style.transition = "opacity 0.5s ease,margin 0.5s ease";

            var js = document.getElementsByClassName("js")[0];
            var ae = document.getElementsByClassName("ae")[0];
            var ps = document.getElementsByClassName("ps")[0];
            var vue = document.getElementsByClassName("vue")[0];
            var css = document.getElementsByClassName("css")[0];

            vue.style.marginLeft = '12.5vw';
            ps.style.marginLeft = '12.5vw';
            css.style.marginLeft = '-1.5vw';
            js.style.marginLeft = '-2vw';
            // css.style.transition = "margin 0.5s ease";

        },
        mouseLeave1(){
            // alert("on");
            var more = document.getElementsByClassName("studymore")[0];
            var js = document.getElementsByClassName("js")[0];
            var ae = document.getElementsByClassName("ae")[0];
            var ps = document.getElementsByClassName("ps")[0];
            var vue = document.getElementsByClassName("vue")[0];
            var css = document.getElementsByClassName("css")[0];

            more.style.opacity = 0;
            more.style.marginLeft = '0vw';
            ps.style.marginLeft = '12vw';
            more.style.marginRight = '-12vw';
            more.style.transition = "opacity 0.5s ease,margin 0.5s ease";

            vue.style.marginLeft = '13vw';
            css.style.marginLeft = '0vw';
            js.style.marginLeft = '0vw';

        },
        music1(){
            var musicIs = document.getElementsByClassName("music")[0];
            var musicIs2 = document.getElementById("music2");

            if(musicIs.innerHTML == "Music:On"){
                // alert(musicIs.innerHTML);

                musicIs2.pause();
                musicIs.innerHTML = "Music:Off";
            }else{
                // alert(musicIs.innerHTML);

                musicIs2.play();
                musicIs.innerHTML = "Music:On"
            }
            // $("div.music").innerHTML = 'Music:Off';
        },
        toIntro(index_is){
            // $("div.outer").removeClass("outer").addClass("outer_2");
            // this.isChange = index_is;
            // var x = 0;
            // for(; x < 4 ; x++){
            //     document.getElementsByName('nameouter')[x].style.animation = 'rotate1 1s infinite linear';
            // }
        }
      },
    watch:{
          // screenWidth(val){
          //     // 为了避免频繁触发resize函数导致页面卡顿，使用定时器
          //     if(!this.timer){
          //         // 一旦监听到的screenWidth值改变，就将其重新赋给data里的screenWidth
          //         this.screenWidth = val
          //         this.timer = true
          //         let that = this
          //         setTimeout(function(){
          //             // 打印screenWidth变化的值
          //             console.log(that.screenWidth+'Width')
          //             that.timer = false
          //         },400)
          //     }
          // },
        windowsize(val){
            // console.log(val);
              // 为了避免频繁触发resize函数导致页面卡顿，使用定时器
              if(!this.timer){
                  // 一旦监听到的screenWidth值改变，就将其重新赋给data里的screenWidth
                  this.screenWidth = val.screenWidth
                  this.screenHeight = val.screenHeight
                  this.timer = true
                  let that = this
                  setTimeout(function(){
                      // 打印screenWidth变化的值
                      console.log(that.screenWidth+'Width')
                      console.log(that.screenHeight+'Height')
                      that.timer = false
                  },400)
              }
          },
      }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .back_1::-webkit-scrollbar{
    display:none;
  }

  @keyframes circle1 {
    0%{width: 0vw;height: 0vw;border-radius: 0vw}
    100%{width: 20vw;height: 20vw;border-radius: 10vw}
  }
  @keyframes testt
   {
     0% {width: 0vw;height: 0vw;border-radius: 0vw}
     /*50% {transform: rotate(180deg);}*/
     100% {width: 7.6vw;height: 7.6vw;border-radius: 3.8vw}
   }

  @keyframes rotate_start {
    0%{transform: scale(0.5,0.5);}
    100%{transform: scale(1,1)}
  }
  @keyframes rotate1
  {
    0% {opacity: 0}
    /*50% {transform: rotate(180deg);}*/
    100% {opacity: 1}
  }
  @keyframes rotate2
  {
    0% {opacity: 0}
    /*50% {transform: rotate(225deg);}*/
    100% {opacity: 1}
  }
  @keyframes rotate3
  {
    0% {opacity: 0}
    /*50% {transform: rotate(270deg);}*/
    100% {opacity: 1}
  }
  @keyframes rotate4
  {
    0% {opacity: 0}
    /*50% {transform: rotate(315deg);}*/
    100% {opacity: 1}
  }
  @keyframes rotate1_2
  {
    0% {opacity: 100%}
    50% {opacity: 0%}
    100% {opacity: 100%}
  }

  .cutoff{
    /*background-image: repeating-linear-gradient(60deg,#a6dadd,#a6dadd 1.5%, white 2%,white 3.5%);*/
  }
  .title1,.title2,.title3{

    font-family: "Source Han Serif SC";
    font-size: 1.2vw;
    position: absolute;
    bottom:50%;
    left:20vw;
    width: 15vw;
    height: 1vw;
    color: black;
    margin-left:3vw ;
  }
  .title1{
    font-size: 2vw;
    font-weight: bold;
    margin-left:-3.5vw ;
    margin-bottom: 0.9vw;

    /*font-style: oblique;*/
  }
  .title3{
    margin-left:-10.5vw;
    color: #a6dadd;
    margin-bottom: -0.5vw;
  }
  .beian{
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    margin-bottom: 10px;
    font-family: "Source Han Serif SC";
    font-size: 14px;
    color: #383838;
  }
  .js{
    transition: margin 0.5s ease;
  }
  .vue,.ae{
    color:white;-webkit-text-stroke: 1px #a6dadd;
    transition: margin 0.5s ease;
  }
  .vue{
    margin-left: 13vw;
    margin-top: -2vw;
  }
  .ae{
    margin-top: -1.6vw;
    margin-left: -6vw;
    font-size: 2.5vw;
    transition: margin 0.5s ease;
  }
  .ps{
    font-size: 1vw;
    margin-left: 12.3vw;
    margin-top: -2vw;
    transition: margin 0.5s ease;
  }
  .css{
    font-size: 2.8vw;
    margin-top: -0.6vw;
    transition: margin 0.5s ease;
  }


  .studymore{
    pointer-events: auto;
    width: 15vw;
    height: 10vw;
    color: #a6dadd;
    /*background-color: #a6dadd;*/
    position: relative;
    float: right;
    font-family: "Source Han Serif SC";
    font-weight: bold;
    font-size: 2vw;
    opacity: 0;
    margin-top: 5vw;
    margin-right: -12vw;
  }

  .music{
    color: white;
    font-family: "Source Han Serif SC";
    font-size: 0.8vw;
    letter-spacing: 1px;
    font-weight: bold;
    line-height: 3vw;
    vertical-align: center;
    position: absolute;
    right: 1.5vw;
    top:1.5vw;
    border-radius: 0.5vw;
    width: 7vw;
    height: 3vw;
    background-color: #c5c5c5;
    box-shadow: 5px 5px 6px #ececec;
  }
  .music:hover{
    background-color: #a8a8a8;
  }
  .music:active{
    transition: background-color 0.5s ease;
    background-color: #a6dadd;
  }


  .outer_2{
    /*background-color: red;*/
    pointer-events: none;
    width: 32vw;
    height: 32vw;
    text-align: center;
    transform: rotate(45deg);
    position: absolute;
    left:50%; top:50%;
    margin-left: -16%;
    margin-top: -16%;
    /*animation: rotate1 1s infinite linear;*/
    transition: transform 1s ease;
  }

  .outer,.outer2,.outer3,.outer4,.outer5{
    pointer-events: none;
    width: 32vw;
    height: 32vw;
    /*border-radius: 10vw;*/
    /*background: #a6dadd;*/
    /*color: #eaffb3;*/
    /*margin: auto;*/
    text-align: center;
    /*transform: rotate(45deg);*/
    position: absolute;
    left:50%; top:50%;
    margin-left: -16%;
    margin-top: -16%;
    /*animation: rotate_start 2s 1 ease;*/
    /*animation: rotate1 2s linear;*/
    /*animation: testt 5s infinite linear;*/

  }
  .outer{
    transform: rotate(45deg);
    animation: rotate1 2s ease;
    /*animation-delay: 0.5s;*/
  }.outer2{
    transform: rotate(90deg);
    animation: rotate2 2s ease;
       /*animation-delay: 0.5s;*/
  }
  .outer3{
     transform: rotate(135deg);
    animation: rotate3 2s ease;
    /*animation-delay: 0.5s;*/
  }
  .outer4{
    transform: rotate(180deg);
    animation: rotate4 2s ease;
    /*animation-delay: 0.5s;*/

  }
  .outer5{
    transform: rotate(0deg);
    /*background-color: #ececec;*/
    width: 44vw;
    height: 44vw;
    margin-left: -22%;
    margin-top: -22%;
    /*animation: rotate4 30s infinite linear;*/
  }

  .circle_study,.circle_blog,.circle_works,.circle_other{
    color: white;
    font-family: "Source Han Serif SC";
    font-weight: bold;
    pointer-events: auto;
    width: 7.6vw;
    height: 7.6vw;
    background: #808080;
    border-radius: 3.8vw;
    margin: 0 auto;
    float: left;

    box-shadow: 5px 5px 10px #e2e2e2;

    /*animation: testt 1s ease;*/
    /*position: absolute;*/
  }

  .circle_study {
    /*animation: testt 1s infinite linear;*/
    transform: rotate(200deg);
    /*animation-delay: 1s;*/
    /*opacity: 0.5;*/
  }
  .circle_blog{
    /*animation-delay: 0.75s;*/
  }
  .circle_works{
    /*animation-delay: 0.5s;*/
  }
  .circle_other{
    /*animation-delay: 0.25s;*/
  }
 /* .circle_study:hover {*/
 /*   animation-play-state: paused;*/
 /*   background: #a6dadd;*/
 /*   transition: background-color 0.2s linear;*/
 /* }*/
 /* .circle_blog:hover {*/
 /*   background: #a6dadd;*/
 /*   animation-play-state: paused;*/
 /*   !*transition: background-color 0.5s linear;*!*/
 /*   transition: background-color 0.2s linear;*/
 /* }*/

 /*.circle_works:hover {*/
 /*  background: #a6dadd;*/
 /*   animation-play-state: paused;*/
 /*  transition: background-color 0.2s linear;*/

 /*}*/
  .circle_other:hover,.circle_works:hover,.circle_blog:hover,.circle_study:hover {
    background: #a6dadd;
    animation-play-state: paused;
    transition: background-color 0.2s linear;
  }

  .circle_other:active,.circle_works:active,.circle_blog:active,.circle_study:active {
    background: #92c1d9;
    /*animation-play-state: paused;*/
    transition: background-color 0.05s linear;
  }

  /*.circle_blog{*/
  /*  background: #6a6a6a;*/
  /*}*/
  /*.circle_works{*/
  /*  background: #6a6a6a;*/
  /*}*/
  /*.circle_other{*/
  /*  background: #6a6a6a;*/
  /*}*/
  .centercircle{
    width: 20%;
    height: 20vw;
    border-radius: 10vw;
    background: #a6dadd;
    color: white;
    margin: auto;
    text-align: center;
    position: absolute;
    left:0; right:0; top:0; bottom:0;
    animation: circle1 1s ease;
    box-shadow: 5px 5px 10px #e2e2e2;
    transition: border-radius 0.5s ease,width 0.5s ease,height 0.5s ease;

    /*top: 0;*/
  }

  .centercircle:hover{
    width: 22%;
    height: 22vw;
    border-radius: 11vw;

  }

  .centercircle2{
    width: 92%;
    height: 92%;
    border-radius: 46%;
    background: #c5c5c5;
    color: white;
    margin: 0 auto;
    position: relative;
    top: 4%;
    transition: border-radius 0.5s ease,width 0.5s ease,height 0.5s ease,top 0.5s ease,background-color 0.5s ease;

  }

  .centercircle2:hover{
    width: 96%;
    height: 96%;
    border-radius: 48%;
    top: 2%;

  }

  .centercircle3{
    width: 96%;
    height: 96%;
    border-radius: 48%;
    background: white;
    color: white;
    margin: 0 auto;
    position: relative;
    top: 2%;
    background-image: url("../assets/20180317105848_IMG_4658-01.jpg");
    background-size: 22vw 22vw;
  }

  .back_1 {
    height: 100%;
    width: 100%;
    background-image: url(../assets/background1.jpg);
    /*background: #2c3e50;*/
    /*opacity: 50%;*/
    text-align: center;
    position: absolute;
    /*z-index_is: 0;*/
  }

  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>

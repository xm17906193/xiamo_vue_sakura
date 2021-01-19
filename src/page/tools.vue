<template>
  <div class="tools">
    <div class="background">
      <img src="https://xiamo.oss-cn-shenzhen.aliyuncs.com/gitee-mashiro/3.png" />
    </div>
    <div class="tools-title">
      <div><span>1</span>.cubic-bezier（贝塞尔曲线）</div>
    </div>
    <div class="tools-content">
      <div>
        <div class="social-icon">
          <img
            src="https://cdn.jsdelivr.net/gh/moezx/cdn@3.1.9/img/Sakura/images/sns/github.png"
          />
          <div class="social-background"></div>
        </div>
      </div>
      <div>
        <div class="social-icon">
          <img
            src="https://cdn.jsdelivr.net/gh/moezx/cdn@3.1.9/img/Sakura/images/sns/qq.png"
          />
          <div class="social-background"></div>
        </div>
      </div>
      <div>
        <div class="social-icon">
          <img
            src="https://cdn.jsdelivr.net/gh/moezx/cdn@3.1.9/img/Sakura/images/sns/bilibili.png"
          />
          <div class="social-background"></div>
        </div>
      </div>
      <div>
        <div class="social-icon">
          <img
            src="https://cdn.jsdelivr.net/gh/moezx/cdn@3.1.9/img/Sakura/images/sns/wangyiyun.png"
          />
          <div class="social-background"></div>
        </div>
      </div>
      <div>
        <div class="social-icon">
          <img
            src="https://cdn.jsdelivr.net/gh/moezx/cdn@3.1.9/img/Sakura/images/sns/email.svg"
          />
          <div class="social-background"></div>
        </div>
      </div>
    </div>
    <div class="tools-code">
      <div class="ql-container ql-snow ql-bar">
        <div class="ql-editor" v-html="content"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "tools",
  data() {
    return {
      content:""+'<pre class="ql-syntax" spellcheck="false">css:  transition: left 0.5s cubic-bezier(0.32, -0.02, 0.58, 1.49),top 0.5s cubic-bezier(0.32, -0.02, 0.58, 1.49);\n' +
      ""+'<span style="color:rgb(80,132,85)">//  https://cubic-bezier.com/?#.32,-0.02,.58,1.49  在线调试</span>\n' +
        "</pre>",
      editorOption: {
        placeholder: "编辑文章内容",
      },
      next_blog_img: "https://xiamo.oss-cn-shenzhen.aliyuncs.com/gitee-mashiro/10.jpg",
      next_blog_title: "emmmmmm",
      colors: ["208,182,213", "139,108,163", "159,198,232", "120,185,176"],
    };
  },
  methods: {},
  mounted() {
    window.scrollTo(0, 0);
    this.$parent.$refs.headbar.jsHover = true;
  },
  destroyed() {
    this.$parent.routerLink = this.$router.currentRoute.fullPath;
  },
};
</script>

<style scoped>
.background {
  height: 400px;
  margin: 90px -8px -8px;
  overflow: hidden;
}

.background img {
  width: 100%;
}

.ql-bar {
  border: unset !important;
}

.tools {
  height: 1500px;
  margin-bottom: 300px;
}

.tools-content {
  min-height: 150px;
  height: auto;
  width: 800px;
  margin: 20px auto 0px;
  border-radius: 10px;
  box-shadow: 0px 0px 12px rgba(0, 0, 0, 0.4);
  overflow: hidden;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
}

.tools-content > div {
  position: relative;
}

.social-icon {
  height: 80px;
  width: 80px;
  /* background: rgba(85, 191, 252, 0.3); */
  background: unset;
  box-shadow: 0px 1px 10px rgba(0, 0, 0, 0.2);
  position: absolute;
  position: absolute;
  left: 0;
  right: 0;
  margin: 35px auto 0 auto;
  border-radius: 10px;
  z-index: 9;
  overflow: hidden;
}

.social-icon > img {
  height: 25px;
  width: 25px;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
  z-index: 9;
  animation: icon-change-out 0.1s;

  /* background: unset;
  border-radius: 100%;
  padding: 5px;
  transition: background 0.3s; */
}

.social-icon:hover > img {
  animation: icon-change 0.3s ease-out;
  height: 30px;
  width: 30px;
  /* background: white;
  transition: background 0.3s; */
}

@keyframes icon-change {
  0% {
    height: 25px;
    width: 25px;
  }
  90% {
    height: 32px;
    width: 32px;
  }
  100% {
    height: 30px;
    width: 30px;
  }
}

@keyframes icon-change-out {
  0% {
    height: 30px;
    width: 30px;
  }
  100% {
    height: 25px;
    width: 25px;
  }
}

.social-background {
  height: 110px;
  width: 110px;
  /* background: rgba(85, 191, 252, 0.3); */
  background: rgba(192, 192, 192, 0.411);
  position: absolute;
  position: absolute;
  left: -230px;
  right: 0;
  bottom: 0;
  top: 150px;
  margin: 20px auto 0 auto;
  border-radius: 10px;
  z-index: 1;
  transform: rotate(45deg);
  transition: left 0.5s cubic-bezier(0.32, -0.02, 0.58, 1.49),
    top 0.5s cubic-bezier(0.32, -0.02, 0.58, 1.49);
}

.social-icon:hover .social-background {
  left: -15px;
  top: -35px;
  transition: all 0.5s cubic-bezier(0.32, -0.02, 0.58, 1.49);
}

.tools-title {
  height: 30px;
  width: 800px;
  margin: 70px auto 0px;
  position: relative;
}

.tools-title span {
  font-size: 20px;
  font-weight: bold;
}

.tools-title > div::before {
  content: "";
  width: 0px;
  height: 3px;
  position: absolute;
  bottom: 0;
  background: rgba(254, 150, 0, 1);
  transition: width 0.3s;
}

.tools-title:hover > div::before {
  width: 240px;
  transition: width 0.3s;
}

.tools-code {
  height: auto;
  width: 800px;
  margin: 20px auto 0px;
  position: relative;
}
</style>

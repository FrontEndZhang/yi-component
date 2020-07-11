<template>
  <div class="nav-bar">
    <div class="nav-bar-left" :style="{color}">
      <slot name="left">
        <span class="iconfont nav-bar-left-icon">&#xe601;</span>
        <span>返回</span>
      </slot>
    </div>

    <div class="nav-bar-center">
      <slot name="center">
        <span>
          <p>我是标题</p>
        </span>
      </slot>
    </div>

    <div class="nav-bar-right" :style="{color}">
      <slot name="right">
        <span>分享</span>
      </slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavBar",
  props : {
    color : {
      type : String,
      default : "#1989fa"
    }
  }
};
</script>
<style scoped lang="less">
@import "./navbar.less";
</style>
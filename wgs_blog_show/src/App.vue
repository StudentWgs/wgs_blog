<script setup lang="ts">
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import { useRouter, useRoute } from "vue-router";
// import HelloWorld from './components/HelloWorld.vue'
const router = useRouter();
const route = useRoute();
// 默认导航0
const activeIndex = ref("0");
// 导航
const handleSelect = (key: string, keyPath: string[]) => {
  console.log(key, keyPath);
  if (keyPath[0] === "0") {
    router.push({
      name: "home",
    });
  } else if (keyPath[0] === "1") {
    router.push({
      name: "blog",
    });
  } else {
    console.log("登录");
  }
};
</script>

<template>
  <nav>
    <el-menu
      :default-active="activeIndex"
      class="el-menu-demo"
      mode="horizontal"
      :ellipsis="false"
      @select="handleSelect"
    >
      <el-menu-item class="margin-left20" index="0">关于</el-menu-item>
      <div class="flex-grow" />
      <el-menu-item index="1">blog</el-menu-item>
      <el-menu-item class="margin-right20" index="2">登录</el-menu-item>
    </el-menu>
  </nav>

  <article>
    <RouterView />
  </article>
</template>

<style scoped lang="scss">
.el-menu--horizontal {
  .el-menu-item:first-child {
    margin-left: 20%;
  }
  .el-menu-item:last-child {
    margin-right: 20%;
  }
}
.flex-grow {
  flex-grow: 1;
}
article {
  margin: 20px 20%;
  box-shadow: 0 0 2px #b5b5b5;
}
</style>

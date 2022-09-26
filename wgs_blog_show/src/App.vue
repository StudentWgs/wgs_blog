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
      <el-menu-item index="0">关于</el-menu-item>
      <div class="flex-grow" />
      <el-menu-item index="1">blog</el-menu-item>
      <el-menu-item index="2">登录</el-menu-item>
    </el-menu>
  </nav>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header> -->

  <RouterView />
</template>

<style scoped>
.flex-grow {
  flex-grow: 1;
}
</style>

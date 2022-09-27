<template>
  <!-- <h1>简历</h1> -->
  <article>
    <section>
      <div class="my-info _flex">
        <div class="info">
          <p>wgs</p>
          <p>1年以内 | 大专 | 离职-随时到岗</p>
          <p>17728264539</p>
        </div>
        <div class="touxiang">
          <el-avatar
            src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png"
          />
        </div>
      </div>
    </section>

    <section v-for="i in list" :key="i.title">
      <p class="Jianli-title">{{ i.title }}</p>
      <div>
        <!-- 工作经历 -->
        <div class="strongtext" v-for="(works, index) in i.works" :key="index">
          {{ works.gongsi }}
          <span class="time">{{ works.time }}</span>
          <div>
            <span>{{ works.suoshu }}</span> |
            <span>{{ works.job }}</span>
          </div>
          工作内容：
          <ul class="texthui">
            <li v-for="i in works.content" :key="i">{{ i }}</li>
          </ul>
        </div>
        <ul>
          <li v-for="(items, index) in i.content" :key="index">
            {{ items }}
          </li>
        </ul>
        <!-- 项目经历 -->
        <div
          class="strongtext"
          v-for="(project, index) in i.project"
          :key="index"
        >
          <p>
            {{ project.title }} <span class="time">{{ project.time }}</span>
          </p>
          <p>{{ project.job }}</p>
          内容：
          <ul class="texthui">
            <li v-for="(i, index) in project.content" :key="index">
              {{ i }}
            </li>
          </ul>
        </div>
        <!-- 教育经历 -->
        <div class="strongtext">
          <p>
            {{ i.school }} <span class="time">{{ i.time }}</span>
          </p>
          <p>{{ i.zhuanye }}</p>
        </div>
      </div>
    </section>
  </article>
</template>

<script setup lang="ts">
import { reactive } from "vue";
// interface List {
//   [index: number]: Object;
// }
// type headType = [
//   {
//     title: string;
//     content: Array<any>;
//     works: Array<{
//       gongsi: string;
//       time: string;
//       suoshu: string;
//       job: string;
//       content: Array<string>;
//     }>;
//     project: Array<{
//       title: string;
//       time: string;
//       job: string;
//       content: Array<string>;
//     }>;
//     school: string;
//     time: string;
//     zhuanye: string;
//   }
// ];
const list = reactive([
  {
    title: "个人技能",
    content: [
      "熟悉基础三件套。",
      "熟悉es6语法",
      "熟悉vue2全家桶，vue周边element-ui，vant，能够快速上手不熟悉的库。",
      "了解原生小程序，uniapp",
      "了解node，webpack",
    ],
  },
  {
    title: "工作经历",
    works: [
      {
        gongsi: "凯利集成（广东）控股有限公司",
        time: "2022-03-2022-07",
        suoshu: "信息部",
        job: "web前端",
        content: [
          "了解项目，业务流程，与后端人员，UI  设计师进行沟通共同协作",
          "根据设计稿还原静态页面",
          "调用接口测试为后续开发功能做准备",
          "负责公司模块功能的交互开发",
          "向上级汇报问题",
        ],
      },
      {
        gongsi: "若趣乐（广州）文化科技有限公司",
        time: "2021-06-2021-09",
        suoshu: "信息技术部",
        job: "前端开发工程师",
        content: [
          "与其他人员交流设计实现需求效果",
          "主要负责部分模块前端开发",
          "完成测试过程的bug，研究解决部分难点等",
          "完成了第一版的上线，及后续的迭代更新",
        ],
      },
    ],
  },
  {
    title: "项目经历",
    project: [
      {
        title: "凯利集成在线签约管理系统",
        time: "2022-03-2022-07",
        job: "前端开发",
        content: [
          "凯利集成小程序以及后台管理系统，移动端的后台管理系统。是一个关于投资理财签约方面的小程序，通过后台工作人员对客户签约的项目进行把控，与小程序之间交互完成客户的签约",
          "技术栈：vue 脚手架，vuerouter，element-Ul，vuex等",
          "项目管理工具svn",
          "负责小程序及后台管理系统h5移动端的静态页面编写",
          "后台管理系统负责部分模块的页面以及独自完成公司管理模块交互功能",
          "调用接口完成对后台信息的增删改查",
        ],
      },
      {
        title: "豆豆快团",
        time: "2021-07-2021-09",
        job: "前端开发",
        content: [
          "该项目分为两部分：",
          "1. 豆豆快团是一个款移动端的项目，有网页版及小程序版。主打开团的商城类应用程序，由团长开启商品售卖，会员可以帮卖并取得佣金;",
          "2. 快团联盟，一个客户可自定义豆豆快团轮播信息，页面部分布局，色彩等",
          "豆豆快团：",
          "技术栈：vue全家桶，vant库等",
          "主要为负责完成ui的还原以及调用接口完成数据交互，修改bug。",
          "用户模块的实现，实现个人数据的收藏，关注展示，收货地址，不同会员等级展示呈现不同的功能。",
          "商品详情页面，购物弹出的展示及功能交互实现。",
          "对其他模块修改bug。",

          "快团联盟：",
          "技术栈：vue3，vite，vant3等",
          "只负责了静态页面",
          "问题：页面采用用户可自定义色彩方案。由于使用组件库无法修改部分组件ui的原色。",
          "采用原生dom方法解决问题等。",
        ],
      },
    ],
  },
  {
    title: "教育经历",
    school: "私立华联学院",
    time: "2019-2022.06",
    zhuanye: "计算机应用技术 | 大专",
  },
]);
</script>

<style src="./Jianli.scss" lang="scss" scoped></style>

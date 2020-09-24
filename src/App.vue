<template>
  <div>
    <LikeHeader headerText="スト">
      <template v-slot:title>
        <p>タイトル</p>
      </template>

      <h1>トータルのいいね数</h1>
      <p>{{age}}</p>
    </LikeHeader>

    <hr />

    <p>ブログの内容</p>

    <hr />

    <LikeNumber :age="age" @my-click="number = $event"></LikeNumber>

    <hr />

    <p>これより下で学習</p>
    <button @click="currentComponent = 'Home'">HOME</button>
    <button @click="currentComponent = 'About'">ABOUT</button>
    <component :is="currentComponent"></component>
  </div>
</template>

<script>
import LikeHeader from "./components/LikeHeader.vue";
import Home from "./components/Home.vue";
import About from "./components/About.vue";

export default {
  components: {
    LikeHeader: LikeHeader,
    Home: Home,
    About: About
  },
  data: function () {
    return {
      age: 6,
      number: 8,
      currentComponent: 'Home'
    };
  },
};
</script>

<style>
</style>

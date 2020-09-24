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
    <hr>
    <div>
      <h2>イベントのフォーム</h2>
      <label for="title">タイトル</label>
      <input 
        type="text" 
        id="title"
        v-model.lazy="evettDate.title"
        >
        <p>{{evettDate.title}}</p>
      <label for="maxNumber">最大人数</label>
      <input 
        type="number" 
        id="maxNumber"
        v-model.number="evettDate.maxNumber"
        >
        <p>{{evettDate.maxNumber}}</p>
    </div>
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
      currentComponent: 'Home',
      evettDate: {
        title: 'タイトル',
        maxNumber: 0
      }
    };
  },
};
</script>

<style>
</style>

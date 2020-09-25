<template>
  <div>
    <LikeHeader headerText="スト">
      <template v-slot:title>
        <p>タイトル</p>
      </template>

      <h1>トータルのいいね数</h1>
      <p>{{ age }}</p>
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
    <hr />
    <div>
      <h2>イベントのフォーム</h2>
      <label for="title">タイトル</label>
      <input type="text" id="title" v-model.lazy="evettDate.title" />
      <p>{{ evettDate.title }}</p>
      <label for="maxNumber">最大人数</label>
      <input
        type="number"
        id="maxNumber"
        v-model.number="evettDate.maxNumber"
      />
      <p>{{ evettDate.maxNumber }}</p>
      <label for="host">主催者</label>
      <input type="text" id="host" v-model="evettDate.host" />
      <p>{{ evettDate.host }}</p>
      <label for="detail">イベント内容</label>
      <textarea type="text" id="detail" v-model="evettDate.detail"></textarea>
      <pre>{{ evettDate.detail }}</pre>

      <input type="checkbox" id="isPrivate" v-model="evettDate.isPrivate" />
      <label for="isPrivate">非公開</label>
      <p>{{ evettDate.isPrivate }}</p>

      <p>参加条件</p>
      <input type="checkbox" id="10" value="10代" v-model="evettDate.target" />
      <label for="10">10代</label>
      <input type="checkbox" id="20" value="20代" v-model="evettDate.target" />
      <label for="20">20代</label>
      <input type="checkbox" id="30" value="30代" v-model="evettDate.target" />
      <label for="30">30代</label>
      <p>{{ evettDate.target }}</p>

      <p>参加費</p>
      <input type="radio" id="free" value="無料" v-model="evettDate.price" />
      <label for="free">無料</label>
      <input type="radio" id="pay" value="有料" v-model="evettDate.price" />
      <label for="pay">有料</label>
      <p>{{ evettDate.price }}</p>

      <p>開催場所</p>
      <select v-model="evettDate.location">
        <option v-for="location in locations" :key="location">{{location}}</option>
      </select>
      <p>{{evettDate.location}}</p>
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
    About: About,
  },
  data: function () {
    return {
      age: 6,
      number: 8,
      currentComponent: "Home",
      locations: ['東京', '大阪', '名古屋'],
      evettDate: {
        title: "タイトル",
        maxNumber: 0,
        host: "takshi",
        detail: "イベント内容",
        isPrivate: false,
        target: [],
        price: "無料",
        location: '東京'
      },
    };
  },
};
</script>

<style>
</style>

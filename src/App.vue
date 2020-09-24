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
    <Poyo>
      
    </Poyo>
  </div>
</template>

<script>
import LikeHeader from "./components/LikeHeader.vue";
import Poyo from "./components/Poyo.vue";

export default {
  components: {
    LikeHeader: LikeHeader,
    Poyo: Poyo,
  },
  data: function () {
    return {
      age: 6,
      number: 8,
    };
  },
};
</script>

<style>
</style>

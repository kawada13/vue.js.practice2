<template>
  <div>
    <LikeHeader></LikeHeader>
    <hr>
    <p>ブログの内容</p>
    <hr>
    <LikeNumber :age="age" @my-click="number = $event"></LikeNumber>
    <hr>
    <p>{{number}}</p>
  </div>
</template>

<script>
import LikeHeader from "./components/LikeHeader.vue";

export default {
  components: {
    LikeHeader: LikeHeader,
  },
  data: function() {
    return {
      age: 6,
      number: 8
    }
  }
};
</script>

<style>
</style>

<template>
  <div>
    <LikeHeader></LikeHeader>
    <hr>
    <p>ブログの内容</p>
    <hr>
    <LikeNumber :age="age"></LikeNumber>
    <LikeNumber></LikeNumber>
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
      age: 6
    }
  }
};
</script>

<style>
</style>

<template>
  <div>
    <p>いいね({{number}})</p>
    <button @click="increment">+1</button>
  </div>
</template>

<script>
export default {
  data:function() {
    return {
      number: 32,
    };
  },
  methods: {
    increment:function(){
      this.number += 1;
    },
  },
};
</script>

<style>
</style>

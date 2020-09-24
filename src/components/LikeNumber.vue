<template>
  <div>
    <p>いいね({{number}})</p>
    <button @click="increment">+1</button>
    <p>{{age}}</p>
    <p>{{halfNumber}}</p>
  </div>
</template>

<script>
export default {
  props: ['age'],
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
  computed: {
    halfNumber: function() {
      return this.age / 2;
    }
  }
};
</script>

<style>
</style>

<template>
  <div>
    <p>{{con}}だよ〜</p>
    <p>{{headerText}}</p>
    <slot name="title"></slot>
    <slot></slot>
    
  </div>
</template>

<script>
export default {
data: function() {
  return {
    con: 'ブログのヘッダー'
  }
},
props: ['headerText']
}
</script>
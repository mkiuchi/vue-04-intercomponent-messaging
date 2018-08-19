<template>
  <div class="hello mdl-layout mdl-js-layout mdl-layout--fixed-header">
    <!--子コンポーネントからのイベントを v-on:(イベント名)="(実行するメソッド)" で捕捉 -->
    <mkheader v-on:additem="additem()" v-on:removeitem="removeitem()"></mkheader>
    <main class="mdl-layout__content">
      <div v-for="item of items" :key="item.number">
        <mkline v-bind:row="item.number"></mkline>
      </div>
    </main>
  </div>
</template>

<script>
/* eslint-disable */
import mkHeader from "./mkHeader.vue"
import mkLine from "./mkLine.vue"

export default {
  name: 'HelloWorld',
  components: {
    'mkheader': mkHeader,
    'mkline': mkLine
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      numitem: 2,
      items: [
        { number: 1 },
        { number: 2 }
      ]
    }
  },
  methods: {
    additem: function () {
      console.log("add-item event received")
      var newnumber = this.numitem + 1
      this.items.push({ number: newnumber })
      this.numitem = newnumber
    },
    removeitem: function () {
      console.log("remove-item event received")
      this.items.pop()
      this.numitem = this.numitem - 1
    }
  }
}
</script>

<style>
</style>

<template>
  <!-- ヘッダー -->
  <header class="mdl-layout__header">
    <div class="mdl-layout__header-row">
      <!-- タイトル文 -->
      <span class="mdl-layout-title">Vue.js inter-component value update</span>

      <!-- スペーサーを入れて後ろのナビゲーション部を右寄せにする -->
      <div class="mdl-layout-spacer"></div>

      <!-- ナビゲーション部 -->
      <nav class="mdl-navigation">
        <!-- リストに要素を追加するボタン -->
        <button class = "mdl-button mdl-js-button mdl-button--fab mdl-js-ripple-effect mdl-button--colored" id="addbutton" style="background-color:#85f7b7;" v-on:click="add()"><i class = "material-icons">add_circle_outline</i><span class="mdl-tooltip" data-mdl-for="addbutton">要素を追加</span></button>

        <!-- リストから要素を削除するボタン -->
        <button class = "mdl-button mdl-js-button mdl-button--fab mdl-js-ripple-effect mdl-button--colored" id="removebutton" style="background-color:#85f7b7;" v-on:click="remove()"><i class = "material-icons">remove_circle_outline</i><span class="mdl-tooltip" data-mdl-for="removebutton">要素を削除</span></button>
      </nav>
    </div>
  </header>
</template>

<script>
/* eslint-disable */
export default {
  name: 'mkHeader',
  methods: {
    add: function () {
      // 親コンポーネント(HelloWorld.vue)にイベントを送信
      this.$emit('additem')
    },
    remove: function () {
      // 親コンポーネント(HelloWorld.vue)にイベントを送信
      this.$emit('removeitem')
    }
  }
}
</script>

<template>
  <div class="mdl-grid">
    <div class="mdl-cell mdl-cell--2-col graybox">
      Item-{{ row.toString() }}
    </div>
    <div class="mdl-cell mdl-cell--2-col graybox">
        <button class = "mdl-button mdl-js-button mdl-button--fab mdl-js-ripple-effect mdl-button--colored" v-on:click="clicked()"><i class = "material-icons">{{ thisrow }}</i></button>
    </div>
    <div class="mdl-cell mdl-cell--4-col graybox">
      <div class="mdl-textfield mdl-js-textfield">
        <input class = "mdl-textfield__input" type="text" v-model="textval"/>
        <!--<label class = "mdl-textfield__label" for="text1">some text goes here...</label>-->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'mkLine',
  data () {
    return {
      textval: '',
      thisrow: ''
    }
  },
  props: ['row'],
  mounted: function () {
    console.log(this.row)
    console.log(this.$options.name)
    console.log(this._uid)
    if (this.row === 1) {
      this.thisrow = 'looks_one'
    } else if (this.row === 2) {
      this.thisrow = 'looks_two'
    } else if (this.row === 3) {
      this.thisrow = 'looks_3'
    } else if (this.row === 4) {
      this.thisrow = 'looks_4'
    } else if (this.row === 5) {
      this.thisrow = 'looks_5'
    } else if (this.row === 6) {
      this.thisrow = 'looks_6'
    } else {
      this.thisrow = 'add_box'
    }
  },
  methods: {
    clicked: function (event) {
      console.log(event)
      if (this.textval === '') {
        this.textval = 'clicked'
      } else {
        this.textval = ''
      }
    }
  }
}
</script>

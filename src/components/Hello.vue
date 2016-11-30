<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <h2>Essential Links</h2>
        <ul>
            <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
            <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
            <li><a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a></li>
            <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
            <br>
            <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
        </ul>
        <h2>Ecosystem</h2>
        <mt-actionsheet
          :actions="actions"
          v-model="sheetVisible">
        </mt-actionsheet>
        <ul>
            <li>
              <i class="icon iconfont icon-appreciate"></i>
              <div class="name">appreciate</div>
              <div class="fontclass">.icon-appreciate</div>
            </li>
            <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
            <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
            <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
            <li><a @click="handleClick">awesome-vue</a></li>
        </ul>
        <mt-switch v-model="value"></mt-switch>

    </div>
</template>

<script>
  import { Toast } from 'mint-ui'
  import { Actionsheet } from 'mint-ui';

  export default {
    name: 'hello',
    data () {
      var that = this
      return {
        msg: 'Welcome to Your Vue.js App',
        value: true,
        sheetVisible: false,
        actions:[{
          name: 'actions1',
          method: function(){
            that.action1()
          }
        },{
          name: 'actions2',
          method: function(){
            console.log('actions2')
          }
        }]
      }
    },
    methods: {
      handleClick: function () {
        this.sheetVisible = true
        console.log(this.sheetVisible)
        // Toast({
        //   message: '提示112123213211111',
        //   position: 'bottom',
        //   duration: 5000
        // })
      },
      action1: function () {
        console.log('actions1')
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

    .h1, h2 {
        background: green;
        position: absolute;
        width: 200px;
        top: 0;
        bottom: 0;
        left: 0;

    .ul {
        color: red;
    }

    }

    h1, h2 {
        font-weight: normal;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>

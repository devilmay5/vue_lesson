<template>
  <div>
    <div>
      <p>
        原始字符串：{{message}}
      </p>
      <p>
        反转后的字符串：{{reverseMessage}}
      </p>
      <input v-model="message">
      <button v-on:click="fanzhuan">反转字符串</button>
    </div>
    <br/>

    <div v-html="html_msg"></div>
    <div v-bind:class="{'class1':is_used}" v-bind:id="'sb'+id"></div>
    <br/>

    <div>
      <pre><a v-bind:href="url">菜鸟教程</a></pre>
    </div>
    <div v-if="is_used">我是一个彩笔</div>
    <div v-else>谁说的，我是大佬</div>
    <button v-on:click="changeUsed(is_used)">点啊
    </button>
    <br/>

    <div v-for="(item,key,index) in list">
      {{index}}.....{{key}}---{{item.id}}={{item.name}}
    </div>
    <ul>
      <li v-for="n in 10">
        {{ n }}
      </li>
    </ul>
    <br/>

    <div>
      计数器：{{countnum}}
      <button v-on:click="changeCount">加数</button>
    </div>
    <br/>

    <router-link :to="{ path: '/Form'}">跳转Form</router-link>

  </div>
</template>

<script>

  export default {
    name: 'Test',
    data: function () {
      return {
        message: '兔儿兔耳朵兔',
        html_msg: '<b>哈哈哈哈哈</b>',
        is_used: false,
        url: 'http://www.runoob.com',
        id: 11,
        countnum: 0,
        list: {
          'st1': {
            'id': 1,
            'name': 'zz'
          },
          'st2': {
            'id': 2,
            'name': 'bb'
          },
          'st3': {
            'id': 3,
            'name': 'cc'
          }
        }
      }
    },
    computed: {
      reverseMessage: {
        get: function () {
          return this.message.split('').reverse().join('')
        },
        set: function (msg) {
          this.message = msg
        }
      }
    },
    watch: {
      countnum: function (val) {
        alert(val)
      }
    },
    methods: {
      // eslint-disable-next-line camelcase
      changeUsed (is_used) {
        // eslint-disable-next-line camelcase,eqeqeq
        if (is_used == true) {
          this.is_used = false
        } else {
          this.is_used = true
        }
      },
      fanzhuan () {
        this.message = this.message.split('').reverse().join('')
      },
      changeCount () {
        return ++this.countnum
      }
    }
  }
</script>

<style scoped>
  .class1 {
    width: 100px;
    height: 200px;
    background-color: #ff0000;
  }
</style>

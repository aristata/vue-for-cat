<template>
  <div class="hello">
    <p>{{ message.value }}</p>
    <p>{{ message.value.length }}</p>
    <p>{{ list[2] }}</p>
    <p>{{ list[num] }}</p>
    <div v-bind:text-content.prop="message2"></div>
    <div v-bind:scroll-top.prop="scroll"></div>
    <pre>{{ $data }}</pre>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data () {
      return {
        message: {
          value: 'Hello Vue.js!'
        },
        list: [
          '사과', '바나나', '딸기'
        ],
        num: 1,
        message2: 'v-bind 장식자',
        scroll: 0
      }
    },
    mounted () {
      this.scroll = 100
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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

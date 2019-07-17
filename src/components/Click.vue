<template>
  <div>
    <p>{{ count }}번 클릭했습니다.</p>
    <button v-on:click="increment">카운트 하기</button>
  </div>
</template>

<script>
  export default {
    name: 'Click',
    data () {
      return {
        count: 0
      }
    },
    methods: {
      increment () {
        this.count += 1
      }
    }
  }
</script>

<style scoped>

</style>

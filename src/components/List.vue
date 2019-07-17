<template>
  <div>
    <ul>
      <li v-bind:class="{ strong:item.hp > 300 }" v-bind:key="item.id" v-for="(item, index) in list">
        ID.{{ item.id }} {{ item.name }} HP.{{ item.hp }}
        <span v-if="item.hp > 300"> 강하다!</span>

        <!-- 리스트에서 요소 제거하기 -->
        <button v-on:click="doRemove(index)">몬스터 제거하기</button>
      </li>
    </ul>
    <br>
    <ul>
      <li v-bind:key="item.id" v-for="item in list" v-if="item.hp < 300">
        ID.{{ item.id }} {{ item.name }} HP.{{ item.hp }}
      </li>
    </ul>

    <!-- 리스트에 요소 추가하기 -->
    <label for="nameInput">이름: </label>
    <input id="nameInput" v-model="name">
    <button v-on:click="doAdd">몬스터 추가하기</button>
  </div>
</template>

<script>
  export default {
    name: 'List',
    data () {
      return {
        name: '키메라',
        list: [
          { id: 1, name: '슬라임', hp: 100 },
          { id: 2, name: '고블린', hp: 200 },
          { id: 3, name: '드래곤', hp: 500 }
        ]
      }
    },
    methods: {
      doAdd () {
        let max = this.list.reduce((a, b) => {
          return a > b.id ? a : b.id
        }, 0)

        this.list.push({
          id: max + 1,
          name: this.name,
          hp: 500
        })
      }
    },
    doRemove (index) {
      // 전달받은 인덱스 위치에서 한 개만큼 제거하기
      this.list.splice(index, 1)
    }
  }
</script>

<style scoped>

</style>

<template>
  <div>
    <ul>
      <li v-for="item in arr" :key="item">{{ item }}</li>
    </ul>
    <button @click="reverse">数组翻转</button>
    <button @click="slice">截取前3个元素</button>
    <button @click="change">更新第一个元素</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1, 2, 3, 4, 5]
    }
  },
  methods: {
    reverse() {
      this.arr.reverse();
      console.log(this.arr);
    },
    slice() {
      this.arr.slice(0, 3)
      console.log(this.arr.slice(0, 3));
    },
    change(){
      this.$set(this.arr,0,1000)
      console.log(this.arr);
    }
  }
}
</script>

<style>
</style>
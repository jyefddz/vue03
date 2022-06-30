<template>
  <div>
    <ul>
      <li v-for="item in stuArr" :key="item.id">{{ item.name }}-{{ item.sex }}-{{ item.hobby }}</li>
    </ul>
    <br>
    <ul>
      <li v-for="(item, key) in tObj" :key="item">{{ item }}-{{ key }}</li>
    </ul>
    <br>
    <ul>
      <li v-for="item in count" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      stuArr: [
        {
          id: 1001,
          name: "孙悟空",
          sex: "男",
          hobby: "吃桃子",
        },
        {
          id: 1002,
          name: "猪八戒",
          sex: "男",
          hobby: "背媳妇",
        },
      ],
      tObj: {
        name: "小黑",
        age: 18,
        class: "1期",
      },
      count: 10
    }
  }
}
</script>

<style>
</style>
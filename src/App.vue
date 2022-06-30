<template>
  <div>
    <p :class="{ active: activeFlag }" class="ppp">我是摩拉克斯,你有带钱吗</p>
    <button @click="activeFlag = !activeFlag">click me</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeFlag: false
    }
  }
}
</script>

<style>
.active {
  color: rgb(0, 225, 255);
}

.ppp {
  border: 10px solid rgb(190, 244, 159);
}
</style>
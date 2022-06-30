<template>
  <div>
    <p :style="{ color: 'pink', fontSize: '50px' }">我是八重神子,你要看轻小说吗</p>
    <p v-bind:style="{ color: colorValue, fontSize: fontSizeValue }">白鹭公主,神里绫华参上</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colorValue: 'skyblue',
      fontSizeValue: '50px'
    }
  }
}
</script>

<style>
</style>
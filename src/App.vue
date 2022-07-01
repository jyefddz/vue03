<template>
  <div>
    <p>国内网站:粉丝数量:{{ num | upDateNum1 }}</p>
    <p>外国网站:粉丝数量:{{ num | upDateNum2 }}</p>
    <p>时间:{{ time | upDateTime1("YYYY-MM-DD") }}</p>
    <p>时间:{{ time | upDateTime2("YYYY/MM/DD") }}</p>
  </div>
</template>

<script>
import moment from "moment";
export default {
  data() {
    return {
      num: 1876986,
      time: 1636450540055
    }
  },
  filters: {
    upDateNum1(val) {
      return val / 10000 + '万'
    },
    upDateNum2(val) {
      return val / 1000 + '千'
    },
    upDateTime1(val) {
      return moment(val).format("YYYY-MM-DD")
    },
    upDateTime2(val) {
      return moment(val).format("YYYY/MM/DD")
    }
  }
}
</script>

<style>
</style>
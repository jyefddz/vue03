<template>
    <div>
        <ul>
            <li v-for="item in myArr" :key="item">{{ item }}</li>
        </ul>
        <button @click="btn">走一走</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            myArr: ['万叶', '钟离', '魈']
        }
    },
    methods: {
        btn() {
            this.myArr.push(this.myArr[0])
            this.myArr.shift()
        }
    }
}
</script>

<style>
</style>
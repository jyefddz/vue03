<template>
    <div>
        <ul>
            <li v-for="item in arr" :key="item">{{ item }}</li>
            <li v-for="(item, index) in arr" :key="index">{{ item }}-{{ index }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            arr: ['万叶', '钟离', '魈', '达达鸭']
        }
    }
}
</script>

<style>
</style>
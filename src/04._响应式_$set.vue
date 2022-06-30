<template>
    <div>
        <h1>{{ obj.a }}</h1>
        <button @click="change">改变</button>
        <br>
        <h1>{{ obj1 && obj1.a }}</h1>
        <button @click="change1">改变1</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            obj: {
                b: 11,
                c: 12
            },
            obj1: {}
        }
    },
    methods: {
        change() {
            this.$set(this.obj, 'a', 9)
            console.log(this.obj);
        },
        change1() {
            this.obj1 = {
                a: 20
            }
        }
    }
}
</script>

<style>
</style>
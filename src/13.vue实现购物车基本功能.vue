<template>
    <div id="app">
        <table class="tb">
            <tr>
                <th><input type="checkbox" v-model="isAll" />全选</th>
                <th>商品</th>
                <th>单价</th>
                <th>数量</th>
                <th>小记</th>
                <th>操作</th>
            </tr>
            <!-- 循环渲染的元素tr -->
            <tr v-for="item in list" :key="item.id">
                <td><input type="checkbox" v-model="item.c" /></td>
                <td>{{ item.name }}</td>
                <td>{{ item.price }}</td>
                <td>
                    <button @click="subFn(item.id)">-</button>
                    <input type="text" v-model="item.count" />
                    <button @click="addFn(item.id)">+</button>
                </td>
                <td>{{ item.price * item.count }}</td>
                <td><button @click="delFn(item.id)">删除</button></td>
            </tr>

            <tr v-if="list.length === 0">
                <td colspan="4">没有数据咯~</td>
            </tr>
        </table>
        <br />
        <div>
            <button @click="allDelFn">删除选中商品</button>
            <button @click="allClearFn">清空购物车</button>
        </div>
        <br />
        <div style="margin-top: 20px">
            <h2>总价: {{ allPrice }}</h2>
            <p>已经选中商品件数:{{ allCount }} </p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            list: [
                { id: 1, name: "奔驰", price: 90000, count: 0, c: false },
                { id: 2, name: "宝马", price: 70000, count: 0, c: false },
                { id: 3, name: "奥迪", price: 60000, count: 0, c: false },
            ],
        };
    },
    computed: {
        isAll: {
            set(val) {
                this.list.forEach((ele) => (ele.c = val))
            },
            get() {
                return this.list.every((ele) => ele.c)
            }
        },
        allPrice() {
            return this.list.reduce((sum, next) => {
                return sum + next.count * next.price
            }, 0)
        },
        allCount() {
            return this.list.reduce((sum, next) => {
                return sum + next.count
            }, 0)
        }
    },
    methods: {
        delFn(id) {
            const index = this.list.findIndex((ele) => id == ele.id)
            // 删除按钮 - 得到索引, 删除数组里元素
            this.list.splice(index, 1);
        },
        subFn(id) {
            const index = this.list.findIndex((ele) => id == ele.id)
            console.log(index);
            if (this.list[index].count <= 0) return this.list[index].count = 0
            this.list[index].count--
        },
        addFn(id) {
            const index = this.list.findIndex((ele) => id == ele.id)
            // console.log(index);
            this.list[index].count++
        },
        allDelFn() {
            this.list = this.list.filter((ele) => {
                return ele.c !== true
            })
        },
        allClearFn() {
            this.list.splice(0, this.list.length);
        }
    },
};
</script>

<style>
#app {
    width: 600px;
    margin: 10px auto;
}

.tb {
    border-collapse: collapse;
    width: 100%;
}

.tb th {
    background-color: #0094ff;
    color: white;
}

.tb td,
.tb th {
    padding: 5px;
    border: 1px solid black;
    text-align: center;
}

.add {
    padding: 5px;
    border: 1px solid black;
    margin-bottom: 10px;
}
</style>

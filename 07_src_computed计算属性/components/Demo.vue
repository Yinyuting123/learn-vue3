<template>
    <h1>一个人的信息</h1>
    <h2>姓名：</h2>
    <input type="text" v-model="person.name">
    <h2>年龄：</h2>
    <input type="number" name="" id="" v-model="person.age">
    <h2>{{ person.fullInfo }}</h2>
    <h2>信息：</h2>
    <input type="text" v-model="person.fullInfo">
</template>
<script>
import { reactive, computed } from 'vue'
export default {
    name: 'Demo',
    // vue2中的写法，Vue3向下兼容也可以实现
    // computed: {
    //     fullInfo() {
    //         return `姓名：${this.person.name} 年龄：${this.person.age}`
    //     }
    // },
    setup() {
        let person = reactive({
            name: '张三',
            age: 18
        })
        //计算属性——简写(没有考虑计算属性被修改的情况)
        person.fullInfo = computed(() => {
            return `姓名：${person.name} 年龄：${person.age}`
        })
        //计算属性——完整
        person.fullInfo = computed({
            get() {
                return `姓名：${person.name} 年龄：${person.age}`
            },
            set(val) {
                person.name = '李四'
                person.age = 25
            }
        })
        return {
            person
        }
    }
}
</script>
<style>
</style>
<template>
    <h1>总和： {{ sum }}</h1>
    <button @click="sum++">点击+1</button>
    <h2>信息：{{ msg }}</h2>
    <button @click="msg+='!'">修改信息</button>
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <button @click="person.name+='~'">修改姓名</button>
    <button @click="person.age++">增长年龄</button>
</template>
<script>
import { ref, reactive, watch } from 'vue'
export default {
    name: 'Demo',
    setup() {
        let sum = ref(0)
        let msg = ref('你好啊')
        let person = reactive({
            name: '张三',
            age: 18
        })
        // 1.情况一：监视ref所定义的一个响应式数据
        watch(sum, (newVal, oldVal) => {
            console.log('sum变了', newVal, oldVal);
        }, {
            immediate: true
        })
        // 2.情况二：监视ref所定义的多个响应式数据
        watch([sum, msg], (newVal, oldVal) => {
            console.log('sum或msg变了', newVal, oldVal);
        }, {
            immediate: true
        })
        // 3.情况三：监视reactive所定义的一个响应式数据，注意：此处无法正确的获取oldVal
        watch(person, (newVal, oldVal) => {
            console.log('person变了', newVal, oldVal);
        }, {
            immediate: true,
        })

        return {
            sum,
            msg,
            person
        }
    }
}
</script>
<style>
</style>
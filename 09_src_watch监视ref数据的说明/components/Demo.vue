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
        let person = ref({
            name: '张三',
            age: 18
        })
        console.log(sum, 'sum');
        console.log(person, 'person');
        watch(sum, (newVal, oldVal) => {
            console.log('sum变了', newVal, oldVal);
        })
        
        watch(person.value, (newVal, oldVal) => {
            console.log('person变了', newVal, oldVal);
        })

        watch(person, (newVal, oldVal) => {
            console.log('person变了', newVal, oldVal);
        }, {
            deep: true
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
<template>
    <h1>一个人的信息</h1>
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <button @click="test">测试触发一下Demo组件的Hello事件</button>
</template>
<script>
import { ref, reactive } from 'vue'
export default {
    name: 'Demo',
    props: ['msg', 'title'],
    emits: ['hello'],
    setup(props, context) {
        // console.log('----setup props----', props);
        console.log('----setup slots----', context.slots);
        // console.log('----setup context----', context.attrs);
        let person = reactive({
            name: '张三',
            age: 18
        })

        // 方法
        function test() {
            context.emit('hello', 666)
        }
        return {
            person,
            test
        }
    }
}
</script>
<style>
</style>
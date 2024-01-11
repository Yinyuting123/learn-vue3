<template>
  <h1>一个人的信息</h1>
  <h2>姓名：{{ name }}</h2>
  <h2>年龄：{{ age }}</h2>
  <h2>性别：{{ sex }}</h2>
  <button @click="sayHello">说话</button>
  <br>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  
  // 此处测试setup函数，暂时不考虑响应式
  setup() {
    let name = '张三'
    let age = 18
    let sex = '女'

    // 方法
    function sayHello() {
      alert(`我叫${name}，我${age}岁了`)
    }
  
    return {
      name,
      age,
      sex,
      sayHello
    }
  },
  data() {
    return {
      sex: '男'
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

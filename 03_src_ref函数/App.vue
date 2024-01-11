<template>
  <h1>一个人的信息</h1>
  <h2>姓名：{{ name }}</h2>
  <h2>年龄：{{ age }}</h2>
  <h2>性别：{{ sex }}</h2>
  <h3>工作种类：{{ job.type }}</h3>
  <h3>工作薪水：{{ job.salary }}</h3>
  <button @click="changeInfo">修改信息</button>
  <br>
</template>

<script>
import {ref} from 'vue'
export default {
  name: 'App',
  components: {
  },
  setup() {
    let name = ref('张三')
    let age = ref(18)
    let sex = '女'
    let job = ref({
      type: '前端工程师',
      salary: '30K'
    })

    // 方法
    function sayHello() {
      alert(`我叫${name}，我${age}岁了`)
    }
    function changeInfo() {
      // name = '李四'
      // age = 25
      name.value = '李四'
      age.value = 25
      job.value.type = '后端工程师'
      console.log(name, '基本类型');
      console.log(job, '对象类型');
    }
    return {
      name,
      age,
      sex,
      job,
      sayHello,
      changeInfo
    }
  }
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

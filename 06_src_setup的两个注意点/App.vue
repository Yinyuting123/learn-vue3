<template>
  <Demo msg="hello" title="你好" @hello="showHelloMsg">
    <span>传递默认的插槽</span>
    <template v-slot:slot1>
      <span>传递具名插槽</span>
    </template>
  </Demo>
</template>

<script>
import Demo from './components/Demo'
export default {
  name: 'App',
  components: {
    Demo
  },
  setup() {
    function showHelloMsg(val) {
      alert(`你好啊,你触发了hello事件,我收到的参数是:${val}!`)
    }
    return {
      showHelloMsg
    }
  }
}
</script>
<template>
  <div>
    <h1>Vue 组件通信示例</h1>
    <!-- 向 ChildComponentA 传递 prop -->
    <ChildComponentA :message="parentMessage" @updateMessage="handleMessageUpdate" />
    <!-- 使用 provide/inject 向 ChildComponentB 共享状态 -->
    <ChildComponentB />
  </div>
</template>

<script>
import ChildComponentA from './components/ChildComponentA.vue'
import ChildComponentB from './components/ChildComponentB.vue'

export default {
  components: {
    ChildComponentA,
    ChildComponentB
  },
  data() {
    return {
      parentMessage: '来自父组件的消息'
    }
  },
  methods: {
    // 处理从子组件发来的事件
    handleMessageUpdate(newMessage) {
      this.parentMessage = newMessage;
    },
    provide() {
      return {
        sharedMessage: '共享给子组件B的消息'
      }
    }
  }
}
</script>
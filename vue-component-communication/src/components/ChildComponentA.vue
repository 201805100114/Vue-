<template>
    <div>
      <h2>子组件A</h2>
      <p>父组件传来的消息：{{ message }}</p>
      <input v-model="localMessage" placeholder="输入新消息">
      <button @click="sendMessage">发送新消息到父组件</button>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      message: String
    },
    data() {
      return {
        localMessage: ''
      }
    },
    methods: {
      sendMessage() {
        this.$emit('updateMessage', this.localMessage);
      }
    }
  }
  </script>
  
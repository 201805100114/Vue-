<template>
    <div>
      <h2>子组件B</h2>
      <p>从父组件通过 provide/inject 接收到的消息：{{ sharedMessage }}</p>
    </div>
  </template>
  
  <script>
  export default {
    inject: ['sharedMessage']
  }
  </script>
  
<template>
  <div>

  </div>
</template>

<script setup>
import { defineComponent, reactive, onMounted } from 'vue'

// 获取pages.json中的配置
// const pages = reactive(__uniConfig.pages)
onMounted(() => {
  console.log('onMounted', __uniConfig)
})
</script>

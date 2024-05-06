<template>
  <div class="u-page">
    <view v-for="item in btn">
      <button class="up-button" @click="handleClick(item)">
        {{ item.name }}
      </button>
    </view>
  </div>
</template>

<script setup>
import { defineComponent, ref, onMounted } from 'vue'
const btn = ref([
  {
    name: '围棋',
    url: '/pages/tools/weiqi/index'
  },
  {
    name: 'ThreeJs',
    url: '/pages/tools/webGL/index'
  }
])
const handleClick = (item) => {
  console.log(item)
  uni.navigateTo({
    url: item.url
  });
}
onMounted(() => {
})
</script>

<style lang="less" scoped>
.u-page {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  padding: 20px;

  .up-button {
    margin: 10px;
  }
}
</style>
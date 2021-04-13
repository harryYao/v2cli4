<template>
  <div>
    <img alt="test img" :src="img1" >
  </div>
</template>

<script>
import testimg from '../static/imgs/1_2.png'
export default {
  data() {
    return {
      img1: testimg
    }
  }
}
</script>

<style scoped>
img {
  width: 400px;
  height: auto;
}
</style>
<template>
  <el-container>
    <el-header>Header</el-header>
    <el-main>Main
      <img alt="test img" :src="img1" >
      </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
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
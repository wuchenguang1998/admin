<template>
  <el-container style="height: 100%;">
    <el-aside width="auto">
      <CommonAside></CommonAside>
    </el-aside>
    <el-container>
      <el-header>
        <CommonHeader></CommonHeader>
      </el-header>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
  import CommonAside from '../components/commonAside'
  import CommonHeader from '../components/commonHeader'
export default {
  name: "Main",
  components: {
    CommonAside,
    CommonHeader
  },
};
</script>

<style scoped>
.el-header {
  background: #333;
}
.el-main {
  padding-top: 0px;
}
</style>

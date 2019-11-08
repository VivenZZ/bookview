<template>
  <div id="app">
    <el-container>
      <el-header style="height: 100px">
        <MyHeader />
      </el-header>
      <el-container>
        <el-aside style="margin-top: 20px;width: 200px;overflow: hidden;">
          <LeftMenu/>
        </el-aside>
        <el-main>
          <router-view/>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import LeftMenu from './components/LeftMenu'
export default {
  name: 'app',
  components: {
    MyHeader,
    LeftMenu
  }
}
</script>
<style>
  #app{
    width: 1200px;
    margin: 0 auto;
    font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
  }
  .el-pagination.is-background .el-pager li:not(.disabled).active{
    background-color: #d32f2f !important;
  }
  .el-pagination.is-background .el-pager li:not(.disabled):hover{
    color: #d32f2f !important;
  }
</style>

<template>
  <el-row class="header" :gutter="20">
    <el-col :span="6">
      <div class="grid-content bg-purple">
        <img class="logo" src="../assets/logo.png" alt="">
      </div>
    </el-col>
    <el-col :span="12">
      <div class="grid-content bg-purple">
        <div>
          <el-input placeholder="请输入书名/作者名" v-model="searchValue">
            <el-button slot="append" icon="el-icon-search"></el-button>
          </el-input>
        </div>
      </div>
    </el-col>
    <el-col :span="6">
      <div class="grid-content bg-purple bookshelf">
        <a href="">登录</a>|<a href="">书架</a>
      </div>

    </el-col>
  </el-row>
</template>

<script>
export default {
  name: 'MyHeader',
  props: {
    msg: String
  },
  data () {
    return {
      searchValue: ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
  .header{
    padding: 30px 0 30px;
    .logo{
      width: 167px;
      height: 32px;
    }
    .bookshelf{
      text-align: right;
      a{
        line-height: 40px;
        color: #333;
        margin: 0 10px;
        text-decoration: none;
      }
      a:hover{
        color: #d32f2f;
      }
    }
  }
</style>

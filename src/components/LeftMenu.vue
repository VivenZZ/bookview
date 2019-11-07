<template>
    <el-row>
      <el-col :span="20">
        <el-menu default-active="1">
          <el-menu-item index="1">
            <router-link to="/books/all">
              <i class="el-icon-notebook-1"></i>
              <span>全部作品</span>
            </router-link>
          </el-menu-item>
          <el-menu-item index="2">
            <router-link to="/books/xuanhuanxiaoshuo">
              <i class="el-icon-notebook-1"></i>
              <span>奇幻玄幻</span>
            </router-link>
          </el-menu-item>
          <el-menu-item index="3">
            <router-link to="/books/wuxiaxiaoshuo">
              <i class="el-icon-notebook-2"></i>
              <span>武侠仙侠</span>
            </router-link>
          </el-menu-item>
          <el-menu-item index="4">
            <router-link to="/books/lishixiaoshuo">
              <i class="el-icon-notebook-2"></i>
              <span>历史军事</span>
            </router-link>
          </el-menu-item>
          <el-menu-item index="5">
            <router-link to="/books/doushixiaoshuo">
              <i class="el-icon-notebook-2"></i>
              <span>都市娱乐</span>
            </router-link>
          </el-menu-item>
        </el-menu>
      </el-col>
    </el-row>
</template>

<script>
export default {
  name: 'LeftMenu'
}
</script>

<style scoped lang="less">
  .all{
    display: inline-block;
    color: #333333;
    margin: 22px 0 10px 22px;
    text-decoration: none;
    font-size: 24px;
  }
  .el-menu{
    border-right: none;
    .el-menu-item{
      height: 40px;
      line-height: 40px;
      a{
        display: inline-block;
        width: 100%;
        line-height: 40px;
        color: #333333;
        text-decoration: none;
      }
    }
    .el-menu-item.is-active{
      color: #d32f2f;
      a{
        color: #d32f2f;
      }
    }
  }
</style>

<template>
    <el-col id="article">
      <el-col>
        <h1>{{title}}</h1>
      </el-col>
      <el-col :span="24" v-html="text">
      </el-col>
      <el-col class="catalog" :span="24">
        <el-col :span="8">
          <router-link to="">上一章</router-link>
        </el-col>
        <el-col :span="8">
          <router-link to="">目录</router-link>
        </el-col>
        <el-col :span="8">
          <router-link to="">下一章</router-link>
        </el-col>
      </el-col>
    </el-col>
</template>

<script>
export default {
  name: 'Article',
  data () {
    return {
      title: '',
      text: ''
    }
  },
  created () {
    this.$axios.get(`http://localhost:3000/api/bookChapter/${this.chapterId}`).then(res => {
      this.text = res.data.text
      this.title = res.data.title
    })
  },
  computed: {
    chapterId: function () {
      return this.$route.params.chapterId
    }
  }
}
</script>

<style scoped lang="less">
#article{
  font-size: 16px;
  line-height: 36px;
  color: #000;
  text-align: justify;
  background-color: #f7f5f0 !important;
  padding: 25px;
  h1{
    font-size: 32px;
    text-align: center;
    margin-bottom: 50px;
  }
  .catalog{
    text-align: center;
    margin-top: 20px;
    font-size: 22px;
    line-height: 42px;
    div{
      border-top: 1px solid #c5baaf;
    }
  }
}
</style>

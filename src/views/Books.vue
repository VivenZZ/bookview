<template>
  <el-row :gutter="20">
    <el-col class="title">
      <h2>{{title}}</h2>
    </el-col>
    <el-col  class="listbox" :span="24" v-for="(book, index) in books" :key="book.index">
      <BookInfo :imgsrc="book.imgsrc" :name="book.name" :index="index" />
    </el-col>
    <div class="block">
      <span class="demonstration"> </span>
      <el-pagination class="solt"
        background
        layout="prev, pager, next"
        :total="1000">
      </el-pagination>
    </div>
  </el-row>
</template>
<script>
import BookInfo from '../components/BookInfo'
export default {
  name: 'books',
  components: { BookInfo },
  data () {
    return {
      activeName: 'first',
      books: [
        {
          name: '寻龙迷踪',
          age: 23,
          imgsrc: 'http://static.zongheng.com/upload/cover/0c/7b/0c7bb5a316809da6e13118cbf7dbd35a.jpeg'
        },
        {
          name: '一剑朝天',
          age: 26,
          imgsrc: 'http://static.zongheng.com/upload/cover/2e/b2/2eb2c0dbc41553435c21c4ae7b6e611b.jpeg'
        },
        {
          name: '煞气横秋 ',
          age: 26,
          imgsrc: 'http://static.zongheng.com/upload/cover/b1/b7/b1b7fe8c4d03df6f2e2cadb21b344030.jpeg'
        },
        {
          name: '一剑朝天',
          age: 26,
          imgsrc: 'http://static.zongheng.com/upload/cover/2e/b2/2eb2c0dbc41553435c21c4ae7b6e611b.jpeg'
        },
        {
          name: '煞气横秋 ',
          age: 26,
          imgsrc: 'http://static.zongheng.com/upload/cover/b1/b7/b1b7fe8c4d03df6f2e2cadb21b344030.jpeg'
        }
      ]
    }
  },
  methods: {
    handleClick (tab, event) {
      console.log(tab, event)
    }
  },
  computed: {
    title: function () {
      let classId = this.$route.params.classId
      let title = ''
      switch (classId) {
        case 'all':
          title = '全部作品'
          break
        case 'xuanhuanxiaoshuo':
          title = '玄幻小说'
          break
        default:
          title = '正在测试'
      }
      return title
    }
  }
}
</script>
<style scoped lang="less">
  .title{
    h2{
      font-weight: 400;
      font-size: 22px;
      color: #d32f2f;
      margin: 0  0 15px;
    }
  }
  .listbox{
    border: 1px solid #f0f0f0;
    padding: 15px 10px;
    margin-bottom: 10px;
    border-radius: 5px;
  }
</style>

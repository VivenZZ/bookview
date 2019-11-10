<template>
  <el-row :gutter="20">
    <el-tabs v-model="activeName" @tab-click="handleClick">
      <el-tab-pane label="全部" name="first"></el-tab-pane>
      <el-tab-pane label="连载中" name="second"></el-tab-pane>
      <el-tab-pane label="完本" name="third"></el-tab-pane>
    </el-tabs>
    <el-col  class="listbox" :span="24" v-for="(book, index) in books" :key="book.index">
      <BookInfo :bookid="book._id" :numbers="book.numbers" :newChapter="book.newChapter" :hot="book.hot" :status="book.status" :novelclass="book.novelclass" :description="book.description" :imgsrc="'http://localhost:3000' + book.imgPath" :name="book.name" :index="index + indexNumber" />
    </el-col>
    <el-col>
      <div class="block">
        <span class="demonstration"> </span>
        <el-pagination class="solt"
                       background
                       :page-size="5"
                       @current-change="handleCurrentChange"
                       layout="prev, pager, next"
                       :total="count">
        </el-pagination>
      </div>
    </el-col>
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
      books: [],
      indexNumber: 0,
      count: 0,
      status: 0
    }
  },
  methods: {
    handleClick (tab, event) {
      switch (tab.label) {
        case '全部':
          this.status = 0
          break
        case '连载中':
          this.status = 1
          break
        case '完本':
          this.status = 2
          break
      }
      this.handleCurrentChange(1)
    },
    handleCurrentChange (val) {
      this.indexNumber = (val - 1) * 5
      this.$axios.get(`http://localhost:3000/api/books?pageNumber=${val}&classId=${this.classId}&status=${this.status}`).then(res => {
        this.books = res.data.books
        this.count = res.data.count
        this.toTop(50)
      })
    },
    toTop (i) { // 返回顶部
      document.documentElement.scrollTop -= i
      if (document.documentElement.scrollTop > 0) {
        var c = setTimeout(() => this.toTop(i), 16)
      } else {
        clearTimeout(c)
      }
    }
  },
  created () {
    this.$axios.get('http://localhost:3000/api/books?pageNumber=1').then(res => {
      this.books = res.data.books
      this.count = res.data.count
    })
  },
  watch: {
    '$route' (to, from) {
      // 对路由变化作出响应...
      this.handleCurrentChange(1)
    }
  },
  computed: {
    classId: function () {
      return this.$route.params.classId
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
  .block{
    float: right;
  }
</style>

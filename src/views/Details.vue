<template>
  <el-row :gutter="20">
    <BookInfo :numbers="bookDetails.numbers" :newChapter="bookDetails.newChapter" :hot="bookDetails.hot" :status="bookDetails.status" :novelclass="bookDetails.novelclass" :description="bookDetails.description" :imgsrc="'http://localhost:3000' + bookDetails.imgPath" :name="bookDetails.name" :index="-1" />
    <el-col class="chapter-list">
      <el-col class="chapter-list_item" :span="6" v-for="chap in chapter" :key="chap._id">
        <router-link :to="`./${chap.bookId}/${chap._id}`">{{chap.title}}</router-link>
      </el-col>
    </el-col>
  </el-row>
</template>

<script>
import BookInfo from '../components/BookInfo'
export default {
  name: 'details',
  components: { BookInfo },
  data () {
    return {
      bookDetails: {},
      chapter: []
    }
  },
  created () {
    this.$axios.get(`http://localhost:3000/api/book/${this.bookId}`).then(res => {
      this.bookDetails = res.data.bookDetails
      this.chapter = res.data.chapter
    })
  },
  computed: {
    bookId: function () {
      return this.$route.params.bookId
    }
  }
}
</script>
<style lang="less" scoped>
.chapter-list{
  margin-top: 40px;
  .chapter-list_item{
    border-bottom: 1px dashed #eeeeee;
    a{
      font-size: 14px;
      line-height: 34px;
      color: #333333;
      text-decoration: none;
    }
    a:hover{
      color: #d32f2f;
      text-decoration: underline;
    }
  }
}
</style>

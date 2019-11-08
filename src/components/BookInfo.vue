<template>
  <div id="book-info">
    <el-col :span="4">
      <router-link to="/books/book/123456">
        <img :src="imgsrc" alt="">
      </router-link>
    </el-col>
    <el-col :span="20">
      <el-col class="book-details">
        <el-col :span="22">
          <span class="book-name">{{name}}</span>
          <span class="book-type">{{novelclass}}</span>
          <span class="book-status">{{status}}</span>
          <span class="book-word-number">字数：<i>{{numbers}}</i></span>
          <span class="book-recommend">总推荐：<i>{{hot}}</i></span>
        </el-col>
        <el-col :span="2" class="big-number">
          <span :class="index < 3 ? 'active': ''">{{index + 1}}</span>
        </el-col>
      </el-col>
      <el-col class="book-details-text">{{description}}</el-col>
      <el-col>
        <el-col :span="12">
          <a href="" class="new-chapter">最新章节: <i>{{newChapter}}</i></a>
        </el-col>
        <el-col :span="12">
          <span class="read-now">立即阅读</span>
          <span class="join-cart">加入书架</span>
        </el-col>
      </el-col>
    </el-col>
  </div>
</template>

<script>
export default {
  name: 'BookInfo',
  props: [
    'newChapter',
    'hot',
    'status',
    'novelclass',
    'description',
    'imgsrc',
    'name',
    'numbers',
    'index'
  ]
}
</script>

<style scoped lang="less">
#book-info{
.book-details{
.book-name{
  font-size: 24px;
  color: #333333;
  font-weight: bold;
  margin-right: 20px;
}
.book-type, .book-status{
  background-color: #d32f2f;
  color: #fff;
  border-radius: 2px;
  display: inline-block;
  padding: 0 5px;
  height: 20px;
  line-height: 20px;
  margin-right: 10px;
}
.book-status{
  background-color: #05c296;
}
.book-word-number, .book-recommend{
  color: #999;
  margin-right: 10px;
i{
  font-size: 16px;
  color: #333333;
}
}
}
.book-details-text{
  font-size: 14px;
  color: #333;
  line-height: 25px;
  margin: 20px 0 15px 0;
}
.big-number{
  font-size: 18px;
span{
  font-size: 26px;
  color: #999;
}
.active{
  font-size: 30px;
  font-weight: bold;
  color: #d32f2f;
}
}
img{
  width: 100%;
  box-shadow: 0 2px 4px 0 rgba(0,0,0,.2);
}
a{
  color: #000000;
  text-decoration: none;
}
a:link {
  font-size: 12px;
  color: #000000;
  text-decoration: none;
}
a.new-chapter{
  display: inline-block;
  font-size: 14px;
  margin-top: 10px;
  color: #999999;
i{
  color: #05c296;
}
}
a.new-chapter:hover{
i{
  font-size: 14px;
  color: #009c71;
}
}
.read-now{
  display: inline-block;
  font-size: 14px;
  line-height: 36px;
  height: 36px;
  color: #e84848;
  border: 1px solid #edacac;
  border-radius: 2px;
  letter-spacing: 1px;
  width: 120px;
  margin-right: 7px;
  text-align: center;
  cursor: pointer;
}
.join-cart{
  display: inline-block;
  line-height: 38px;
  height: 38px;
  color: #fff;
  background: #d32f2f;
  width: 100px;
  margin-right: 30px;
  text-align: center;
  cursor: pointer;
}
.join-cart:hover{
  background: #e84848;
}
.read-now:hover{
  border: 1px solid #e84848;
  color: #e84848;
}
.solt{
  float: right;
  margin-bottom: 50px;
}
}
</style>

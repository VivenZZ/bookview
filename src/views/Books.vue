<template>
  <el-row :gutter="20">
    <el-col class="title">
      <h2>{{title}}</h2>
    </el-col>
    <el-col  class="listbox" :span="24" v-for="(book, index) in books" :key="book.index">
        <el-col :span="4">
          <router-link to="/">
            <img :src="book.imgsrc" alt="">
          </router-link>
        </el-col>
        <el-col :span="20">
          <el-col class="book-details">
            <el-col :span="20">
              <span class="book-name">{{book.name}}</span>
              <span class="book-type">玄幻奇幻</span>
              <span class="book-status">连载中</span>
              <span class="book-word-number">字数：<i>12.3万</i></span>
              <span class="book-recommend">总推荐：<i>12.3万</i></span>
            </el-col>
            <el-col :span="4" class="big-number">
              第 <span>{{index + 1}}</span>名
            </el-col>
          </el-col>
          <el-col class="book-details-text">
            一道寂灭恒河的枷锁，一滴乱世封天的真血。在万古前挣脱，于混沌中破灭。 红尘的因果颤动了苍茫的锁链，史前的邪族唤醒了域外的冥舟。 弹指间，神魔泣血，乱天动地，诸圣争霸，乾坤碎灭。 万族兴起，天外天临。仙域永夜，古境崩塌。 仙古之道，谁主沉浮？
          </el-col>
          <el-col>
            <el-col :span="12">
              <a href="" class="new-chapter">最新章节: <i>我是一个小程序员</i></a>
            </el-col>
            <el-col :span="12">
              <span class="read-now">立即阅读</span>
              <span class="join-cart">加入书架</span>
            </el-col>
          </el-col>
        </el-col>
    </el-col>
  </el-row>
</template>
<script>
export default {
  name: 'books',
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
        font-size: 30px;
        font-weight: bold;
        color: #d32f2f;
      }
    }
    img{
      max-width: 100%;
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
      width: 220px;
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
  }
</style>

<template>
  <el-row>
    <el-tabs v-model="activeName" @tab-click="handleClick">
      <el-tab-pane label="连载中" name="first"></el-tab-pane>
      <el-tab-pane label="已完本" name="second"></el-tab-pane>
    </el-tabs>
    <el-col  class="listbox" :span="24" v-for="book in books" :key="book.age">
        <el-col :span="4">
          <router-link to="/">
            <img src="../assets/details.jpg" alt="">
          </router-link>
        </el-col>
        <el-col :span="20">
          <el-col class="book-details">
            <el-col :span="21">
              <span class="book-name">{{book.name}}</span>
              <span class="book-type">玄幻奇幻</span>
              <span class="book-status">连载中</span>
              <span class="book-word-number">字数：<i>12.3万</i></span>
              <span class="book-recommend">总推荐：<i>12.3万</i></span>
            </el-col>
            <el-clo :sapn="3">
              <el-badge type="danger" :value="3" class="item">
                <span>已更新</span>
              </el-badge>
            </el-clo>
          </el-col>
          <el-col class="book-details-text">
            一道寂灭恒河的枷锁，一滴乱世封天的真血。在万古前挣脱，于混沌中破灭。 红尘的因果颤动了苍茫的锁链，史前的邪族唤醒了域外的冥舟。 弹指间，神魔泣血，乱天动地，诸圣争霸，乾坤碎灭。 万族兴起，天外天临。仙域永夜，古境崩塌。 仙古之道，谁主沉浮？
          </el-col>
          <p>
            <el-button>立即阅读</el-button>
            <el-button>加入书架</el-button>
          </p>
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
          name: '登临仙姑',
          age: 23
        },
        {
          name: 'kevin',
          age: 26
        },
        {
          name: 'kevin',
          age: 26
        },
        {
          name: 'kevin',
          age: 26
        },
        {
          name: 'kevin',
          age: 26
        }
      ]
    }
  },
  methods: {
    handleClick (tab, event) {
      console.log(tab, event)
    }
  }
}
</script>
<style scoped lang="less">
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
      margin-top: 20px;
      margin-bottom: 5px;
    }
    img{
      width: 130px;
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
  }
</style>

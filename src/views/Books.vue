<template>
  <el-row>
    <el-tabs v-model="activeName" @tab-click="handleClick">
      <el-tab-pane label="连载中" name="first"></el-tab-pane>
      <el-tab-pane label="已完本" name="second"></el-tab-pane>
    </el-tabs>
    <el-col  class="listbox" :span="24" v-for="book in books" :key="book.age">
      <router-link to="/">
        <el-col :span="4">
          <img src="../assets/details.jpg" alt="">
        </el-col>
        <el-col :span="20">
          <span>{{book.name}}{{$route.params.classId}}</span>
          <el-badge :value="12" class="item">
            <el-button size="small">连载中</el-button>
          </el-badge>
          <el-tag type="danger">玄幻奇幻</el-tag>
          <span>字数：<i>12.3万</i></span>
          <span>总推荐：<i>12.3万</i></span>
          <p>
            一道寂灭恒河的枷锁，一滴乱世封天的真血。在万古前挣脱，于混沌中破灭。 红尘的因果颤动了苍茫的锁链，史前的邪族唤醒了域外的冥舟。 弹指间，神魔泣血，乱天动地，诸圣争霸，乾坤碎灭。 万族兴起，天外天临。仙域永夜，古境崩塌。 仙古之道，谁主沉浮？
          </p>
          <p>
            <el-button>立即阅读</el-button>
            <el-button>加入书架</el-button>
          </p>
        </el-col>
      </router-link>
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
          name: 'viven',
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

<template>
  <el-row :gutter="20">
    <BookInfo :imgsrc="imgsrc" :name="name" :index="index" />
  </el-row>
</template>

<script>
import BookInfo from '../components/BookInfo'
export default {
  name: 'details',
  components: { BookInfo },
  data () {
    return {
      imgsrc: 'http://static.zongheng.com/upload/cover/0c/7b/0c7bb5a316809da6e13118cbf7dbd35a.jpeg',
      name: '一剑朝天',
      index: 0
    }
  }
}
</script>

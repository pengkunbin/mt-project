<template>
  <el-container class="layout_default">
    <el-header height="210px">
      <my-header/>
    </el-header>
    <el-main>
      <nuxt/>
    </el-main>
  <el-footer>
    <my-footer/>
  </el-footer>
</el-container>

</template>
<script>
import MyHeader from '../components/public/header/index.vue'
import MyFooter from '../components/public/footer/index.vue'
export default {
  components:{
    MyHeader,
    MyFooter
  }
}
</script>

<style>
 @import "@/assets/css/public/layout.scss";
</style>

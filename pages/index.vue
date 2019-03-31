<template>
  <div class="page-index">
    <el-row>
      <el-col :span="5">
        <EMenu/>
      </el-col>
      <el-col :span="19">
        <ELife/>
      </el-col>
    </el-row>
    <el-row :span="24">
      <Artistic/>
    </el-row>
    <el-row :span="24">
      <Film/>
    </el-row>
  </div>
</template>

<script>
import EMenu from '../components/index/menu.vue';
import ELife from '../components/index/life.vue';
import Artistic from '../components/index/artistic.vue'
import Film from '../components/index/film.vue'
export default {
  components: {
    EMenu,
    ELife,
    Artistic,
    Film
  },
  layout:'default'
};
</script>

<style lang="scss">
@import '@/assets/css/index/index.scss';
*{
  margin:0;
  padding: 0;
}
</style>

<template>
    <el-row :gutter="0" class="m-header">
        <el-col :span="5">
            <Geo/>
        </el-col>
        <el-col :span="6">
            <User/>
        </el-col>
        <el-col :span="13">
            <Nav/>
        </el-col>
    </el-row>
    
</template>
<script>
import Geo from './geo.vue'
import User from './user.vue'
import Nav from './nav.vue'
export default {
    components:{
        Geo,
        User,
        Nav
    }
}
</script>
<style lang="scss">

</style>

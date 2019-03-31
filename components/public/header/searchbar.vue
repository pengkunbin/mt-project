<template>
  <div class="search-panel">
    <el-row class="m-header-searchbar">
      <el-col :span="3" class="left">
        <img src="//s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png" alt="美团">
      </el-col>
      <el-col :span="16" class="center">
          <div class="wrapper">
              <el-input 
                placeholder="搜索商家或地点"
                v-model="search"
                @focus="focus"
                @blur="blur"
                @input="input">
              </el-input>
              <button class="el-button el-button--primary"><i class="el-icon-search"></i></button>
              <dl 
                class="hotPlace"
                v-if="isHotPlace">
                  <dt>热门搜索</dt>
                  <dd 
                    v-for = "(item,index) in hotPlace"
                    :key = "index"
                  >{{ item }}</dd>
              </dl>
              <dl 
                class="searchList"
                v-if="isSearchList">
                  <dd
                   v-for = "(item,index) in searchList"
                   :key = "index">{{item}}</dd>
              </dl>
          </div>
          <p class="suggest">
              <a href="#">美团外卖</a>
              <a href="#">美团外卖</a>
              <a href="#">美团外卖</a>
              <a href="#">美团外卖</a>
              <a href="#">美团外卖</a>
          </p>
          <ul class="nav">
              <li>
                  <nuxt-link to='/'>美团外卖</nuxt-link>
              </li>
              <li>
                  <nuxt-link to='/'>猫眼电影</nuxt-link>
              </li>
              <li>
                  <nuxt-link to='/'>美团酒店</nuxt-link>
              </li>
              <li>
                  <nuxt-link to='/'>民宿/公寓</nuxt-link>
              </li>
              <li>
                  <nuxt-link to='/'>商家入驻</nuxt-link>
              </li>
              <li>
                  <nuxt-link to='/'>美团公益</nuxt-link>
              </li>
          </ul>
      </el-col>
      <el-col :span="4" class="right">
        <ul class="security">
          <li>
            <i class="refund"/>
            <p class="txt">随时退</p>
          </li>
          <li>
            <i class="single"/>
            <p class="txt">不满意免单</p>
          </li>
          <li>
            <i class="overdue"/>
            <p class="txt">过期退</p>
          </li>
        </ul>
      </el-col>
    </el-row>
  </div>
</template>
<script>
export default {
    data(){
        return{
            search:'',
            isFocus:false,
            hotPlace:['火锅','火锅','火锅'],
            searchList:['故宫','故宫','故宫']
        }
    },
    computed:{
        isHotPlace:function(){
            return this.isFocus&&!this.search
        },
        isSearchList:function(){
            return this.isFocus&&this.search
        }
    },
    methods:{
        focus:function(){
            this.isFocus = true;
        },
        blur:function(){
            this.isFocus = false;
            setTimeout(function(){
                self.isFocus=false
            },200)
        },
        input:function(){
            
        }
    }
};
</script>
<style>
</style>

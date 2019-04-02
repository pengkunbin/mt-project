<template>
    <dl @mouseover="over">
      <dt>{{title}}</dt>
      <dd v-for="(item,index) in options"
          :key="item.type"
          :kind="item.type"
          :keyword="item.keyword"
          :class="{active:kind === item.type}" >
          {{item.keyword}}
      </dd>
      <dd class="all" v-if = "alltrue">
        <span>全部</span>
        <span>></span>
      </dd>
    </dl>
</template>
<script>
export default {
    props:{
        options:{
            type:Array,
            default(){
                return[]
            }
        },
        alltrue:{
            type:String,
            default:'true'
        },
        title:{
            type:String,
            default:""
        },
        cname:{
            type:String,
            default:""
        }
    },
    data(){
        return{
            kind: "zero"
        }
    },
    methods: {
    over: async function(e) {
      let dom = e.target;
      let tag = dom.tagName.toLowerCase();
      
      let self = this;
      if (tag === "dd") {
        this.kind = dom.getAttribute("kind");
        let keyword = dom.getAttribute("keyword");
        console.log(this.kind)
      }
    }
  }
}
</script>
<style>

</style>

<template>
  <section class="m-istyle">
    <Title
    v-bind:title="title.title" 
        v-bind:options="title.options" 
        v-bind:allture="title.allture">
    </Title>
    <ul class="ibody">
      <li
        v-for="item in cur"
        :key="item.title">
        <el-card
          :body-style="{ padding: '0px' }"
          shadow="never">
          <img
            :src="item.img"
            class="image">
          <ul class="cbody">
            <li class="title">{{ item.title }}</li>
            <li class="pos"><span>{{ item.pos }}</span></li>
            <li class="price">￥<em>{{ item.price }}</em><span>/起</span></li>
          </ul>
        </el-card>
      </li>
    </ul>
  </section>
</template>
<script>
import Title from './title.vue' 
export default {
  components:{
    Title
  },
  data: () => {
    return {
      title:{
      title: "有格调",
      options: [
        {
          type: "zero",
          keyword: "全部"
        },
        {
          type: "part",
          keyword: "约会聚餐"
        },
        {
          type: "spa",
          keyword: "丽人SPA"
        },
        {
          type: "movie",
          keyword: "电影演出"
        },
        {
          type:"travel",
          keyword:"品质出游"
        }
      ],
    },
      kind: 'all',
      list: {
        all: [{
          img:"https://p1.meituan.net/msmerchant/a316aecb8e8db3a2dda8e7d7f93137a41454100.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/msmerchant/a316aecb8e8db3a2dda8e7d7f93137a41454100.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/msmerchant/a316aecb8e8db3a2dda8e7d7f93137a41454100.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/msmerchant/a316aecb8e8db3a2dda8e7d7f93137a41454100.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/msmerchant/a316aecb8e8db3a2dda8e7d7f93137a41454100.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/msmerchant/a316aecb8e8db3a2dda8e7d7f93137a41454100.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        }],
        part: [
          {
          img:"https://p0.meituan.net/merchantpic/aa71c104353e5a8ed8ba03c376d03e0554748.png@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/merchantpic/aa71c104353e5a8ed8ba03c376d03e0554748.png@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/merchantpic/aa71c104353e5a8ed8ba03c376d03e0554748.png@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/merchantpic/aa71c104353e5a8ed8ba03c376d03e0554748.png@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/merchantpic/aa71c104353e5a8ed8ba03c376d03e0554748.png@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/merchantpic/aa71c104353e5a8ed8ba03c376d03e0554748.png@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        }
        ],
        spa: [{
          img:"https://p0.meituan.net/wedding/fdaa77486382c4b7da77a43b4ce95c2d4837727.png@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/wedding/fdaa77486382c4b7da77a43b4ce95c2d4837727.png@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/wedding/fdaa77486382c4b7da77a43b4ce95c2d4837727.png@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/wedding/fdaa77486382c4b7da77a43b4ce95c2d4837727.png@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/wedding/fdaa77486382c4b7da77a43b4ce95c2d4837727.png@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/deal/cd10a8c174aeaef4ca1bb357a9962f4a244542.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        }],
        movie: [{
          img:"https://p0.meituan.net/deal/cd10a8c174aeaef4ca1bb357a9962f4a244542.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/deal/cd10a8c174aeaef4ca1bb357a9962f4a244542.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/deal/cd10a8c174aeaef4ca1bb357a9962f4a244542.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/deal/cd10a8c174aeaef4ca1bb357a9962f4a244542.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p0.meituan.net/deal/cd10a8c174aeaef4ca1bb357a9962f4a244542.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/tdchotel/642a2a393c335bd0624fb81074baccf5103512.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        }],
        travel: [{
          img:"https://p1.meituan.net/tdchotel/642a2a393c335bd0624fb81074baccf5103512.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/tdchotel/642a2a393c335bd0624fb81074baccf5103512.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/tdchotel/642a2a393c335bd0624fb81074baccf5103512.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/tdchotel/642a2a393c335bd0624fb81074baccf5103512.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/tdchotel/642a2a393c335bd0624fb81074baccf5103512.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        },{
          img:"https://p1.meituan.net/tdchotel/642a2a393c335bd0624fb81074baccf5103512.jpg@460w_260h_1e_1c",
          title:"必胜客（中心书城店）",
          pos:"【随新享丰盛3人餐A010】1份",
          price:"249"
        }]
      }
    }
  },
  computed: {
    cur: function () {
      return this.list[this.kind]
    }
  },
  async mounted(){
    // let self=this;
    // // let {status,data:{count,pois}}=await self.$axios.get('/search/resultsByKeywords',{
    // //   params:{
    // //     keyword:'景点',
    // //     city:self.$store.state.geo.position.city
    // //   }
    // // })
    // if(status===200&&count>0){
    //   let r= pois.filter(item=>item.photos.length).map(item=>{
    //     return {
    //       title:item.name,
    //       pos:item.type.split(';')[0],
    //       price:item.biz_ext.cost||'暂无',
    //       img:item.photos[0].url,
    //       url:'//abc.com'
    //     }
    //   })
    //   self.list[self.kind]=r.slice(0,9)
    // }else{
    //   self.list[self.kind]=[]
    // }
  },
  methods: {
    over: async function (e) {
      let dom = e.target
      let tag = dom.tagName.toLowerCase()
      let self = this
      if (tag === 'dd') {
        this.kind = dom.getAttribute('kind')
        let keyword = dom.getAttribute('keyword')
      //   let {status,data:{count,pois}}=await self.$axios.get('/search/resultsByKeywords',{
      //     params:{
      //       keyword,
      //       city:self.$store.state.geo.position.city
      //     }
      //   })
      //   if(status===200&&count>0){
      //     let r= pois.filter(item=>item.photos.length).map(item=>{
      //       return {
      //         title:item.name,
      //         pos:item.type.split(';')[0],
      //         price:item.biz_ext.cost||'暂无',
      //         img:item.photos[0].url,
      //         url:'//abc.com'
      //       }
      //     })
      //     self.list[self.kind]=r.slice(0,9)
      //   }else{
      //     self.list[self.kind]=[]
      //   }
      // }
      }
    }
  },

}
</script>
<style lang="scss">
    @import "@/assets/css/index/artistic.scss";
</style>
<template>
  <div class="m-menu">
    <dl 
        class="nav" 
        @mouseleave="mouseleave">
        <dt>全部分类</dt>
        <dd 
            v-for="(item,index) in menu" 
            :key="index"
            @mouseenter="enter">
            <i :class="item.type"/>
                {{ item.name }}
            <span class="arrow"/>
        </dd>
    </dl>
    <div 
        v-if="kind"
        class="detail"
        @mouseenter="sover"
        @mouseleave="sout">
        <template v-for="(item,index) in curdetail.child">
            <h4 :key="index">{{item.title}}</h4>
            <span
                v-for="v in item.child"
                :key="v">{{v}}</span>
        </template>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      menu: [
        {
          type: "food",
          name: "美食",
          child: [
            {
              title: "美食",
              child: ["代金券", "甜点饮品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        },
        {
          type: "takeout",
          name: "外卖",
          child: [
            {
              title: "外卖",
              child: ["美团外卖"]
            }
          ]
        },
        {
          type: "hotel",
          name: "酒店",
          child: [
            {
              title: "酒店星级",
              child: ["经济型", "舒适/三星", "高档/四星", "豪华/五星"]
            }
          ]
        },{
          type:"homestay",
          name:"榛果民宿",
          child:[
            {
              title:'热门城市',
              child:["上海","成都","北京","重庆","南京","杭州","广州","西安","大连"]
            }
          ]
        },{
          type:"movie",
          name:"猫眼电影",
          child:[
            {
              title:'热映电影',
              child:["人间·喜剧小飞象","海市蜃楼","反贪风暴4","比悲伤更悲伤的故事","老师·好雷霆沙赞！","惊奇队长","波西米亚狂想曲","精灵怪物：疯狂之旅"]
            },{
              
            }
          ]
        },{
          type:"airport",
          name:"机票 / 火车票",
          child:[
            {
              title:'机票',
              child:["国内机票","国际/港澳台机票"]
            }
          ]
        },{
          type:"ktv",
          name:"休闲娱乐 / KTV",
          child:[
            {
              title:'休闲娱乐',
              child:["足疗按摩","洗浴/汗蒸","酒吧","密室逃脱","轰趴馆","茶馆","私人影院","DIY手工坊","采摘/农家乐","网吧网咖","游乐游艺","VR桌面游戏","真人CS","棋牌室","其他玩乐"]
            }
          ]
        },{
          type:"life",
          name:"生活服务",
          child:[{
            title:'生活服务',
            child:["衣物/皮具","洗护家政","搬家运输","送水","充值缴费","服饰/鞋包","养护","开锁换锁","居家维修","管道疏通","家电维修清洗","电脑维修","手机","维修证件照/肖像","摄影照片","冲印/图文文印","商务服务/法律服务","文化传媒机构","成人用品/情趣用品"]
          }]
        },{
          type: "hair",
          name: "丽人/美发/医学美容",
          child: [
            {
              title: "丽人",
              child: ["美发","美甲","美睫","美容","美体","医学美容","瑜伽,","舞蹈","瘦身","纤体","韩式定妆","祛痘","纹身","化妆品","养发"]
            }
          ]
        },{
          type:"marry",
          name:"结婚 / 婚纱摄影 / 婚宴",
          child:[
            {
              title:'结婚',
              child:["婚纱摄影","旅拍","个性写真","婚宴婚庆公司","婚纱礼服西服定制","婚戒首饰","婚车租赁","司仪主持","彩妆造型","婚礼跟拍","婚礼小礼品","更多婚礼服务"]
            }
          ]
        },{
          type: "offspring",
          name: "亲子 / 儿童乐园 / 幼教",
          child: [
            {
              title: "美食",
              child: ["代金券", "甜点饮品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        },{
          type: "sport",
          name: "运动健身 / 健身中心",
          child: [
            {
              title: "美食",
              child: ["代金券", "甜点饮品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        },{
          type: "furniture",
          name: "家装 / 建材 / 家居",
          child: [
            {
              title: "美食",
              child: ["代金券", "甜点饮品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        },{
          type: "study",
          name: "学习培训 / 音乐培训",
          child: [
            {
              title: "美食",
              child: ["代金券", "甜点饮品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        },{
          type: "health",
          name: "医疗健康 / 宠物 / 爱车",
          child: [
            {
              title: "美食",
              child: ["代金券", "甜点饮品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        },{
          type: "bar",
          name: "酒吧 / 密室逃脱",
          child: [
            {
              title: "美食",
              child: ["代金券", "甜点饮品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        }
      ],
      kind:''
    };
  },
  computed:{
      curdetail:function(){
          return this.menu.filter((item) => item.type === this.kind)[0]
      }
  },
  methods:{
      mouseleave:function(){
          let self = this;
          self._timer = setTimeout(function(){
              self.kind=''
          },150)
      },
      enter:function(e){
          this.kind = e.target.querySelector('i').className;
      },
      sover:function(){
        clearTimeout(this._timer)
      },
      sout:function(){
        this.kind=''
      }
  }
};
</script>
<style>
</style>

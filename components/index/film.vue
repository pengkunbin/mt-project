<template>
  <section class="f-istyle">
    <dl @mouseover="over">
      <dt>猫眼电影</dt>
      <dd :class="{active:kind === 'hot'}" kind="hot" keyword="正在热映">正在热映</dd>
      <dd :class="{active:kind === 'about'}" kind="about" keyword="即将上映">即将上映</dd>
      <dd class="all">
        <span>全部</span>
        <span>></span>
      </dd>
    </dl>

    <article class="filmbody">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item,index) in cur" :key="index" class="slider-item-film">
          <img :src="item.img" class="item">
          <div class="film-info">
            <p class="film-score">
              <b>3456789</b>人想看
            </p>
            <p class="film-name">调音师</p>
            <span class="buy-ticket">预售</span>
          </div>
        </swiper-slide>

        <div class="swiper-pagination" slot="pagination"></div>
        <div class="swiper-button-prev" slot="button-prev"></div>
        <div class="swiper-button-next" slot="button-next"></div>
      </swiper>
    </article>
  </section>
</template>
<script>
export default {
  data() {
    return {
      swiperOption: {
        slidesPerView: 5,
        spaceBetween: 20,
        slidesPerGroup: 2,
        loop: true,
        loopFillGroupWithBlank: true,
        pagination: {
          el: ".swiper-pagination",
          clickable: true
        },
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev"
        }
      },
      list: {hot:[
        {
          img:
            "https://p0.meituan.net/movie/b9784931b6212e633978298fd827142b316254.jpg@267w_371h_1e_1c"
        },
        {
          img:
            "https://p1.meituan.net/movie/c63849c7a9de360a7b192bc322792a111705236.jpg@267w_371h_1e_1c"
        },
        {
          img:
            "https://p0.meituan.net/movie/210c580200fe1fd5f71efc2cb08049b216821810.jpg@267w_371h_1e_1c"
        },
        {
          img:
            "https://p1.meituan.net/movie/29caaa1b66c95807a3f4d29b5b03644b1876102.jpg@267w_371h_1e_1c"
        },
        {
          img:
            "https://p0.meituan.net/movie/5c59da7d7c06aea763fe5d59bdabf173146948.jpg@267w_371h_1e_1c"
        },
        {
          img:
            "https://p0.meituan.net/movie/3a836076b5227ef5a2059d9844a26098517279.jpg@267w_371h_1e_1c"
        }
      ],about:[
        {
          img:
            "https://p0.meituan.net/movie/3a836076b5227ef5a2059d9844a26098517279.jpg@267w_371h_1e_1c"
        },        {
          img:
            "https://p0.meituan.net/movie/5c59da7d7c06aea763fe5d59bdabf173146948.jpg@267w_371h_1e_1c"
        },
                {
          img:
            "https://p0.meituan.net/movie/b9784931b6212e633978298fd827142b316254.jpg@267w_371h_1e_1c"
        },
        {
          img:
            "https://p1.meituan.net/movie/c63849c7a9de360a7b192bc322792a111705236.jpg@267w_371h_1e_1c"
        },
        {
          img:
            "https://p0.meituan.net/movie/210c580200fe1fd5f71efc2cb08049b216821810.jpg@267w_371h_1e_1c"
        },  
      ]},
      kind: "hot"
    };
  },
  computed:{
      cur: function () {
        return this.list[this.kind]
    }
  },
  methods: {
    over: async function(e) {
      let dom = e.target;
      let tag = dom.tagName.toLowerCase();
      let self = this;
      if (tag === "dd" && dom.getAttribute("class")!=='all') {
        this.kind = dom.getAttribute("kind");
        let keyword = dom.getAttribute("keyword");
      }
    }
  }
};
</script>
<style lang="scss">
@import "@/assets/css/index/film.scss";
</style>

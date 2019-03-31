<template>
  <section class="f-istyle">
    <Title 
        v-bind:title="title.title" 
        v-bind:options="title.options" 
        v-bind:allture="title.allture">
    </Title>
    <article class="filmbody">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item,index) in swiper" :key="index" class="slider-item-film">
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
import Title from "./title.vue";
export default {
  components: {
    Title
  },
  data() {
    return {
    title:{
      title: "猫眼电影",
      options: [
        {
          type: "zero",
          keyword: "正在热映"
        },
        {
          type: "about",
          keyword: "即将上映"
        }
      ],
    },
      allture: "true",
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
      swiper: [
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
      ],
    };
  },
  methods: {}
};
</script>
<style lang="scss">
@import "@/assets/css/index/film.scss";
</style>

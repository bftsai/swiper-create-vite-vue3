<template>
  <h1 class="d-flex align-items-center">This is About page.</h1>
  <!-- <router-link to="/">Home</router-link> |
  <router-link to="/about">About</router-link> -->
  <div class="container">
    <swiper class="mySwiper" :slides-per-view="1" :space-between="50"
      :modules="modules"
      navigation
      :pagination="{ clickable: true }">
      <swiper-slide>
        <img src="https://images.unsplash.com/photo-1514888286974-6c03e2ca1dba?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1443&q=80" alt="">
      </swiper-slide>
      <swiper-slide>
        <img src="https://images.unsplash.com/photo-1494256997604-768d1f608cac?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1529&q=80" alt="">
      </swiper-slide>
      <swiper-slide>
        <img src="https://images.unsplash.com/photo-1478098711619-5ab0b478d6e6?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80" alt="">
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation, Pagination } from 'swiper/modules'

// Import Swiper styles
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';


export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup () {
    return {
      pagination: {
          clickable: true,
          renderBullet: function (index, className) {
            return '<span class="' + className + '">' + (index + 1) + '</span>';
          },
      },
      modules: [Navigation, Pagination],
    }
  },
}
</script>
<style scoped>
.container{
  grid-column: span 2;
  grid-row: span 2;
}
.mySwiper {
  width: 500px;
  height: 400px;
}
.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: #fff;
  color: #000;

  /* Center slide text vertically */
  display: flex;
  justify-content: center;
  align-items: center;
}
.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.swiper-pagination-bullet {
  width: 20px;
  height: 20px;
  text-align: center;
  line-height: 20px;
  font-size: 12px;
  color: #000;
  opacity: 1;
  background: rgba(0, 0, 0, 0.2);
}

.swiper-pagination-bullet-active {
  color: #ffffff;
  background: #007aff;
}
</style>
<template>
  <q-page class="row items-center justify-evenly">
    <swiper
      :slides-per-view="1"
      :space-between="50"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
    >
      <swiper-slide class="slide">Slide 1</swiper-slide>
      <swiper-slide class="slide">Slide 2</swiper-slide>
      <swiper-slide class="slide">Slide 3</swiper-slide>
    </swiper>
  </q-page>
</template>

<script lang="ts">
import { Swiper, SwiperSlide } from 'swiper/vue';
import type { Swiper as SwiperType } from 'swiper';

import 'swiper/css';

import { defineComponent } from 'vue';

export default defineComponent({
  name: 'IndexPage',
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper: SwiperType) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log('slide change');
    };

    return { onSwiper, onSlideChange };
  },
});
</script>

<style scoped>
.slide {
  height: 400px;
  background-color: #00a5ff;
  display: grid;
  place-content: center;
  font-size: 2rem;
  color: white;
}
</style>

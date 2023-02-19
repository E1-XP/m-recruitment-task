<script setup lang="ts">
import { Splide, SplideSlide } from "@splidejs/vue-splide";

import "@splidejs/vue-splide/css";

import mockup0 from "./../assets/images/Mockup.png";
import mockup1 from "./../assets/images/Mockup (1).png";
import mockup2 from "./../assets/images/Mockup (2).png";
import mockup3 from "./../assets/images/Mockup (3).png";
import mockup4 from "./../assets/images/Mockup (4).png";

const slides = [mockup1, mockup4, mockup0, mockup2, mockup3];
</script>

<template>
  <div class="l-container slider">
    <Splide
      :options="{
        perPage: 5,
        type: 'loop',
        start: 2,
        focus: 'center',
        pagination: false,
        width: '80%',
      }"
      aria-label="App mockups"
    >
      <SplideSlide
        v-for="(image, idx) in slides"
        :key="idx"
        class="slider__slide"
      >
        <img :src="image" alt="mobile app mockup" class="slider__image" />
      </SplideSlide>
    </Splide>
    <!-- <button class="slider__btn" @click="slider?.prev">p</button>
    <button class="slider__btn" @click="slider?.next">n</button> -->
  </div>
</template>

<style scoped lang="scss">
.slider {
  /* width: 50%;
  margin: 0 auto; */
  /* height: 27.617rem; */
  display: flex;
  align-items: center;
  justify-content: center;

  &__slide {
    display: flex;
    align-items: center;
    justify-content: center;
    /* transform: scale(0.8); */
    transition: transform 0.2s ease;

    &.is-active {
      transform: scale(1.2);
      z-index: 999;
    }
  }

  &__image {
    /* height: 27.617rem; */
    width: 100%;
  }

  &__btn {
    &:first-of-type {
      order: -1;
    }
  }
}

:global(.splide__track) {
  padding-top: 3rem;
  padding-bottom: 3rem;
}

:global(.splide__list) {
  left: 2%;
  position: relative;
}

:global(.splide__arrow) {
  background-color: transparent;

  & svg {
    fill: $color-primary !important;
  }
}
</style>

<script setup lang="ts">
import { Splide, SplideSlide, SplideTrack } from "@splidejs/vue-splide";

import "@splidejs/vue-splide/css";

import mockup0 from "./../assets/images/Mockup.png";
import mockup1 from "./../assets/images/Mockup (1).png";
import mockup2 from "./../assets/images/Mockup (2).png";
import mockup3 from "./../assets/images/Mockup (3).png";
import mockup4 from "./../assets/images/Mockup (4).png";

const slides = [mockup1, mockup4, mockup0, mockup2, mockup3];
</script>

<template>
  <div class="l-container">
    <Splide
      class="slider"
      :options="{
        perPage: 5,
        type: 'loop',
        start: 2,
        focus: 'center',
        pagination: false,
        width: '60%',
        trimSpace: false,
        breakpoints: {
          700: {
            perPage: 3,
          },
        },
      }"
      :has-track="false"
      aria-label="App mockups"
    >
      <SplideTrack>
        <SplideSlide
          v-for="(image, idx) in slides"
          :key="idx"
          class="slider__slide"
        >
          <img :src="image" alt="mobile app mockup" class="slider__image" />
        </SplideSlide>
      </SplideTrack>
      <div class="splide__arrows">
        <button class="splide__arrow splide__arrow--prev">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="icon icon-tabler icon-tabler-arrow-narrow-right"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            stroke-width="2"
            stroke="#0046cb"
            fill=""
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
            <path d="M5 12l14 0"></path>
            <path d="M15 16l4 -4"></path>
            <path d="M15 8l4 4"></path>
          </svg>
        </button>
        <button class="splide__arrow splide__arrow--next">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="icon icon-tabler icon-tabler-arrow-narrow-right"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            stroke-width="2"
            stroke="#0046cb"
            fill="none"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
            <path d="M5 12l14 0"></path>
            <path d="M15 16l4 -4"></path>
            <path d="M15 8l4 4"></path>
          </svg>
        </button>
      </div>
    </Splide>
  </div>
</template>

<style scoped lang="scss">
.slider {
  margin: 0 auto;
  margin-bottom: 2rem;
  margin-top: 3.5rem;

  &__slide {
    display: inline-flex;
    vertical-align: middle;

    &.is-active {
      .slider__image {
        transform: scale(1.2);
        z-index: 999;
      }
    }
  }

  &__image {
    height: auto;
    width: 100%;
    transition: transform 0.2s ease;
    position: relative;
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

:global(.splide__arrow) {
  background-color: transparent;

  & svg {
    transform: scale(2);
  }
}

:global(.splide__arrow--prev) {
  left: -3em;
}

:global(.splide__arrow--next) {
  right: -3em;
}
</style>

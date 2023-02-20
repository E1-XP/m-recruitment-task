<script setup lang="ts">
import { reactive } from "vue";

import Header from "./header.vue";
import ActionCard from "./actionCard.vue";

interface State {
  activeIdx?: number;
  clickCount: number[];
}

const data = [
  {
    title: "Install the App",
    text: "Big, small, online, offline, local or international. Size doesn’t matter. We work on diverse projects for top brands.",
  },
  {
    title: "Login First",
    text: "Most popular type of partnership. limited liabilities, Size doesn’t work on diverse projects for top brands.",
  },
  {
    title: "Setup Your Profile",
    text: "Popular type of partnership. limited liabilities, in fact, the only Size doesn’t matter. diverse projects for top brands.",
  },
];

const headerData = {
  heading: "How It Work",
  subtitle: "A Simple, Proven Way to Boost Your Team Performance.",
  subtitle2:
    "Most popular type of partnership Malta. The limited liability is, in fact, the only type of company allowed by Companies.",
};

const state = reactive<State>({
  activeIdx: undefined,
  clickCount: data.map((_) => 0),
});

const oncardClick = (idx: number) => {
  if (idx === state.activeIdx) return;

  state.activeIdx = idx;
  state.clickCount[idx] += 1;

  console.log(
    `Card titled "${data[idx].title}" was clicked ${state.clickCount[idx]} times.`
  );
};
</script>

<template>
  <section class="how-it-work">
    <div class="l-container how-it-work__container">
      <Header class="how-it-work__header" :data="headerData" />
      <ul class="how-it-work__list">
        <li
          class="how-it-work__item"
          :class="{ 'how-it-work__item--active': idx === state.activeIdx }"
          v-for="(card, idx) in data"
          v-bind:key="card.title"
          @click="() => oncardClick(idx)"
        >
          <ActionCard :data="card" :idx="idx" />
        </li>
      </ul>
      <figure class="how-it-work__picture">
        <img
          src="./../assets/images/Image.png"
          alt="mobile app mockup"
          class="how-it-work__image"
          draggable="false"
        />
      </figure>
    </div>
  </section>
</template>

<style scoped lang="scss">
.how-it-work {
  margin-bottom: 2rem;

  &__container {
    display: grid;
    grid-template-rows: auto auto;
    grid-template-columns: 1fr 1fr;
  }

  &__header {
    grid-column: 1/3;
    margin: 0 auto;
    margin-top: 2.667rem;
    margin-bottom: 1.821rem;
  }

  &__picture {
    user-select: none;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;

    @include bp($bp-small) {
      grid-column: 1/3;
    }
  }

  &__image {
    pointer-events: none;
    -webkit-user-drag: none;
    height: 100%;
    width: auto;
  }

  &__list {
    width: 23rem;
    justify-self: end;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-top: 1.792rem;
    margin-bottom: 3.583rem;

    @include bp($bp-small) {
      grid-column: 1/3;
      justify-self: center;
    }
  }

  &__item {
    border-radius: 4px;
    position: relative;

    &::before {
      content: "";
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0;
      left: 0;
      box-shadow: $box-shadow;
      opacity: 0;
      z-index: -1;
      transition: opacity 0.3s ease;
    }

    &--active::before {
      opacity: 1;
    }
  }
}
</style>

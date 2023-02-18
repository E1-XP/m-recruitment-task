<script setup lang="ts">
import ActionCard from "./actionCard.vue";

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
</script>

<template>
  <section class="how-it-work">
    <div class="l-container how-it-work__container">
      <header class="how-it-work__header">
        <h2 class="heading h-text-center">How It Work</h2>
        <p class="subtitle h-text-center how-it-work__subtitle">
          A Simple, Proven Way to Boost Your Team Performance.
        </p>
        <p class="subtitle-2">
          Most popular type of partnership Malta. The limited liability is, in
          fact, the only type of company allowed by Companies.
        </p>
      </header>
      <ul class="how-it-work__list">
        <li
          class="how-it-work__item"
          :class="{ 'how-it-work__item--active': idx === 1 }"
          v-for="(card, idx) in data"
          v-bind:key="card.title"
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
  & :global(.l-container) {
    display: grid;
    grid-template-rows: auto auto;
    grid-template-columns: 1fr 1fr;
  }

  &__header {
    grid-column: 1/3;
    margin: 0 auto;
    margin-top: 2.667rem;
    margin-bottom: 1.821rem;
    width: 22.23rem;
  }

  &__subtitle {
    width: 85%;
    margin: 0 auto;
    margin-top: 1.1rem;
    margin-bottom: 0.91rem;
  }

  &__picture {
    user-select: none;
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

    &__item {
      border-radius: 4px;

      &--active {
        box-shadow: $box-shadow;
      }
    }
  }
}
</style>

<template>
  <div></div>
  <div class="q-pa-md">
    <div class="q-col-gutter-md row items-start q-my-lg q-py-lg">
      <CardsComponent v-for="index in 4" :key="index" v-bind="cards[0]" />
    </div>
    <div class="q-col-gutter-md row items-start q-my-lg q-py-lg">
      <CardsComponent v-for="index in 4" :key="index" v-bind="cards[1]" />
    </div>
    <div class="q-col-gutter-md row items-start q-my-lg q-py-lg">
      <CardsComponent v-for="index in 4" :key="index" v-bind="cards[2]" />
    </div>
  </div>
</template>

<script setup>
import CardsComponent from "components/CardsComponent.vue";
import parallaxImage from "../assets/parallax1.jpg";
import mountainsImage from "../assets/mountains.jpg";

import avatarImage from "../assets/avatar.png";
defineOptions({
  name: "IndexPage",
});
const cards = [
  {
    image: parallaxImage,
    avatar: avatarImage,
    title: "Title",
    subtitle: "Subtitle",
    desc: "Description",
  },
  {
    image: mountainsImage,
    avatar: avatarImage,
    title: "Title",
    subtitle: "Subtitle",
    desc: "Description",
  },
  {
    image: parallaxImage,
    avatar: avatarImage,
    title: "Title",
    subtitle: "Subtitle",
    desc: "Description",
  },
];
</script>

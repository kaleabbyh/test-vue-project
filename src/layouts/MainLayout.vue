<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white">
      <q-toolbar class="w-full flex justify-between items-center">
        <div
          class="flex flex-1 justify-center items-center q-pa-sm"
          style="width: 30%"
        >
          <q-btn
            flat
            icon="menu"
            aria-label="Menu"
            class="text-black"
            @click="toggleLeftDrawer"
          />

          <img
            alt="youtube logo"
            src="~assets/youtube.png"
            style="width: 10%; height: 5%"
          />
          <q-toolbar-title class="text-black text-h8">YouTube</q-toolbar-title>
        </div>

        <div
          class="flex items-center justify-center text-black"
          style="width: 60%"
        >
          <div class="relative-position" style="width: 70%">
            <q-input outlined dense rounded placeholder="Search"> </q-input>
            <div class="absolute-top-right flex justify-end items-center">
              <span class="q-mr-md text-grey-6"
                ><q-icon name="keyboard" size="24px"
              /></span>
              <q-btn
                rounded
                flat
                bordered
                class="flex q-pa-sm q-px-lg bg-grey-3"
              >
                <q-icon name="search" />
              </q-btn>
            </div>
          </div>

          <q-icon name="mic" size="15px" class="q-ma-md" />
        </div>

        <div
          class="flex items-center justify-center text-black"
          style="width: 30%"
        >
          <img
            alt="youtube logo"
            src="~assets/theedot.png"
            style="width: 10%; height: 5%"
            class="text-grey-8"
          />
          <div class="relative-position" style="width: 50%">
            <q-input outlined dense rounded> </q-input>
            <div class="flex justify-center items-center">
              <div class="absolute-top-left">
                <q-avatar
                  class="q-ma-sm items-center"
                  color="blue"
                  text-color="white"
                  icon="person"
                  size="24px"
                />
                <span class="q-ml-md text-grey-6"> User </span>
              </div>
            </div>
          </div>

          <q-icon name="notifications" size="15px" class="q-ma-md" />
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered :width="100">
      <q-list>
        <q-item-label header> </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

defineOptions({
  name: "MainLayout",
});

const linksList = [
  {
    title: "Home",
    caption: "Home",
    icon: "home",
    link: "#",
  },
  {
    title: "Music",
    caption: "Music",
    icon: "music_note",
    link: "#",
  },
  {
    title: "History",
    caption: "History",
    icon: "history",
    link: "#",
  },
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>


<style scoped>
.custom-title {
  font-size: 20px; /* Default font size */
}

@media (max-width: 992px) {
  /* Small screens */
  .custom-title {
    font-size: 18px;
  }
}

@media (max-width: 768px) {
  /* Medium screens */
  .custom-title {
    font-size: 16px;
  }
}

@media (max-width: 576px) {
  /* Large screens */
  .custom-title {
    font-size: 12px;
  }
}
</style>

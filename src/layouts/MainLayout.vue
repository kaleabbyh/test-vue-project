<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white">
      <q-toolbar class="w-full flex justify-between items-center">
        <div class="flex flex-1 justify-center items-center q-pa-sm">
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
            style="width: 30px; height: 30px"
          />
          <q-toolbar-title class="text-black text-weight-bold"
            >YouTube</q-toolbar-title
          >
        </div>

        <div
          class="flex items-center justify-center text-black"
          style="width: 60%"
        >
          <div class="relative-position overflow-hidden" style="width: 50%">
            <q-input outlined dense rounded placeholder="Search"> </q-input>
            <div class="absolute-top-right flex justify-end items-center">
              <span class="q-mr-md text-grey-6"
                ><q-icon name="keyboard" size="24px"
              /></span>
              <q-btn
                rounded
                flat
                bordered
                class="flex justify-center items-center q-pa-sm q-px-lg bg-grey-3"
              >
                <q-icon name="search" />
              </q-btn>
            </div>
          </div>

          <q-icon name="mic" size="24px" class="q-ma-md" />
        </div>

        <div class="flex flex-1 justify-center items-center q-pa-sm">
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
            style="width: 30px; height: 30px"
          />
          <q-toolbar-title class="text-black text-weight-bold"
            >YouTube</q-toolbar-title
          >
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>

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
    title: "Docs",
    caption: "quasar.dev",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "Github",
    caption: "github.com/quasarframework",
    icon: "code",
    link: "https://github.com/quasarframework",
  },
  {
    title: "Discord Chat Channel",
    caption: "chat.quasar.dev",
    icon: "chat",
    link: "https://chat.quasar.dev",
  },
  {
    title: "Forum",
    caption: "forum.quasar.dev",
    icon: "record_voice_over",
    link: "https://forum.quasar.dev",
  },
  {
    title: "Twitter",
    caption: "@quasarframework",
    icon: "rss_feed",
    link: "https://twitter.quasar.dev",
  },
  {
    title: "Facebook",
    caption: "@QuasarFramework",
    icon: "public",
    link: "https://facebook.quasar.dev",
  },
  {
    title: "Quasar Awesome",
    caption: "Community Quasar projects",
    icon: "favorite",
    link: "https://awesome.quasar.dev",
  },
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>

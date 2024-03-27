<template>
  <!-- <q-page class="flex flex-center">
    <img
      alt="Quasar logo"
      src="~assets/quasar-logo-vertical.svg"
      style="width: 200px; height: 200px"
    />
  </q-page> -->

  <div class="q-pa-md">
    <div class="q-col-gutter-md row items-start">
      <div class="col-3">
        <q-img src="https://picsum.photos/500/300" />
        image one
      </div>

      <div class="col-3">
        <q-card flat style="border-radius: 8px">
          <q-img src="https://picsum.photos/500/300" />
        </q-card>
        <div class="flex q-pt-sm">
          <q-avatar class="bg-dark text-white"> me</q-avatar>
          <div class="flex column q-pl-sm">
            <span class="text-weight-bold">Title</span>
            <span class="">text</span>
            <span class="text-weight-thin">some text</span>
          </div>
        </div>
        <!-- image two -->
      </div>

      <div class="col-3">
        <q-img src="https://picsum.photos/500/300" />
        image three
      </div>
      <div class="col-3">
        <q-img src="https://picsum.photos/500/300" />
        image 4
      </div>
    </div>
  </div>
</template>

<script setup>
defineOptions({
  name: "IndexPage",
});
</script>

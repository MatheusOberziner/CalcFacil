<template>
  <div class="window-height window-width row justify-center items-center div-video">
    <video
      autoplay
      muted
      loop
      playsinline
      preload="metadata"
      class="bg_video"
    >
      <source
        src="../assets/video.mp4"
        type="video/mp4"
      >
    </video>

    <div class="column">
      <div class="row">
        <q-card
          square
          bordered
          class="shadow-24 q-pb-md"
          style="width: 35vw;"
        >
          <q-card-section class="row justify-between">
            <div class="row items-center q-gutter-md">
              <q-avatar class="bg-primary" style="height: 1.7em; width: 1.7em;">
                <q-img src="../assets/logo.svg" style="height: 70%; width: 70%;" />
              </q-avatar>

              <span class="text-h2 text-primary text-bold">CalcFácil</span>
            </div>

            <div class="row items-center">
              <q-btn outline color="primary" label="documentação" />
            </div>
          </q-card-section>

          <div class="col-12 row justify-center q-pt-xl">
            <q-card bordered class="q-pa-lg" style="width: 70%; background-color: #7d8792;">
              <q-card-section class="q-py-none q-pb-sm" style="background-color: #bfebff;">
                <q-input bordered />
              </q-card-section>

              <q-card-section class="q-px-none">
                <div class="col-12 row q-gutter-sm">
                  <div class="col-6">
                    <q-btn color="orange" style="width: 100%;" />
                  </div>
                  <div class="col-6">
                    <q-btn color="orange" style="width: 100%;" />
                  </div>
                </div>
              </q-card-section>
            </q-card>
          </div>
        </q-card>
      </div>
    </div>
  </div>
</template>
<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage'
})
</script>
<style>
.bg_video{
  float: left;
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: fixed;
}
</style>

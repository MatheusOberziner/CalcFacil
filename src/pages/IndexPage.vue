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
          class="shadow-24 q-pb-lg"
          :style="{
            width: $q.screen.lt.sm ? '90vw' :
                   $q.screen.lt.md ? '70vw' :
                   $q.screen.lt.lg ? '50vw' :
                                     '40vw'
          }"
        >
        <!-- style="width: 40vw;" -->
          <q-card-section class="row justify-between">
            <div class="row items-center q-gutter-md">
              <q-avatar class="bg-primary" :style="$q.screen.lt.sm ? 'height: 1em; width: 1em;' : $q.screen.lt.lg ? 'height: 1.4em; width: 1.4em;' : 'height: 1.7em; width: 1.7em;'">
                <q-img src="../assets/logo.svg" style="height: 70%; width: 70%;" />
              </q-avatar>

              <span class="text-primary text-bold" :class="$q.screen.lt.sm ? 'text-h5' : $q.screen.lt.md ? 'text-h4' : $q.screen.lt.lg ? 'text-h3' : 'text-h2 '">CalcFácil</span>
            </div>

            <div class="row items-center">
              <q-btn outline color="primary" label="documentação" @click="showDocumentation()" />
            </div>
          </q-card-section>

          <div class="col-12 row justify-center q-pt-md">
            <q-card bordered class="q-pa-lg" style="width: 70%; background-color: #7d8792;">
              <q-card-section class="q-py-none q-pb-sm" style="background-color: #bfebff;">
                <q-input bordered readonly v-model="resultLabel" style="font-size: 24px;" />
              </q-card-section>

              <q-card-section class="q-px-none q-pb-none">
                <div class="col-12 row">
                  <template v-for="(button, index) in dataButtons" :key="index">
                    <CustomButton :button="button" />
                  </template>
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
import CustomButton from 'src/components/CustomButton.vue'
import DocumentationDialog from 'src/components/DocumentationDialog.vue'
export default {
  name: 'IndexPage',
  components: { CustomButton },
  data () {
    return {
      result: '',
      resultLabel: '',
      dataButtons: [
        { class: 'col-6 q-pr-xs', color: 'red-9', label: 'CLEAN', style: 'font-size: 16px;', clickHandler: this.clean },
        { class: 'col-6', color: 'red-9', label: 'BACKSPACE', icon: 'backspace', style: 'font-size: 16px;', clickHandler: this.back },

        { class: 'col-3 q-pr-xs', color: 'grey-8', label: 'xⁿ', style: 'font-size: 20px;', clickHandler: () => this.insert('^') },
        { class: 'col-3 q-pr-xs', color: 'grey-8', label: '(', style: 'font-size: 18px;', clickHandler: () => this.insert('(') },
        { class: 'col-3 q-pr-xs', color: 'grey-8', label: ')', style: 'font-size: 18px;', clickHandler: () => this.insert(')') },
        { class: 'col-3', color: 'orange-8', label: '+', style: 'font-size: 20px;', clickHandler: () => this.insert('+') },

        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '1', style: 'font-size: 20px;', clickHandler: () => this.insert('1') },
        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '2', style: 'font-size: 20px;', clickHandler: () => this.insert('2') },
        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '3', style: 'font-size: 20px;', clickHandler: () => this.insert('3') },
        { class: 'col-3', color: 'orange-8', label: '-', style: 'font-size: 26px;', clickHandler: () => this.insert('-') },

        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '4', style: 'font-size: 20px;', clickHandler: () => this.insert('4') },
        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '5', style: 'font-size: 20px;', clickHandler: () => this.insert('5') },
        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '6', style: 'font-size: 20px;', clickHandler: () => this.insert('6') },
        { class: 'col-3', color: 'orange-8', label: 'x', style: 'font-size: 18px;', clickHandler: () => this.insert('x') },

        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '8', style: 'font-size: 20px;', clickHandler: () => this.insert('8') },
        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '7', style: 'font-size: 20px;', clickHandler: () => this.insert('7') },
        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '9', style: 'font-size: 20px;', clickHandler: () => this.insert('9') },
        { class: 'col-3', color: 'orange-8', label: '÷', style: 'font-size: 20px;', clickHandler: () => this.insert('÷') },

        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '.', style: 'font-size: 20px;', clickHandler: () => this.insert('.') },
        { class: 'col-3 q-pr-xs', color: 'grey-9', label: '0', style: 'font-size: 20px;', clickHandler: () => this.insert('0') },
        { class: 'col-6', color: 'blue-10', label: '=', style: 'font-size: 20px;', clickHandler: this.calculate }
      ]
    }
  },
  methods: {
    showDocumentation () {
      this.$q.dialog({
        component: DocumentationDialog,
        parent: this
      })
    },
    insert (char) {
      this.resultLabel += char

      switch (char) {
        case 'x':
          this.result += '*'
          break
        case '÷':
          this.result += '/'
          break
        case '^':
          this.result += '**'
          break
        default:
          this.result += char
          break
      }
    },
    clean () {
      this.resultLabel = ''
      this.result = ''
    },
    back () {
      this.resultLabel = this.resultLabel.substring(0, this.resultLabel.length - 1)
      this.result = this.result.substring(0, this.result.length - 1)
    },
    calculate () {
      if (this.result) {
        try {
          // eslint-disable-next-line no-eval
          this.resultLabel = eval(this.result)
        } catch (error) {
          this.resultLabel = 'Expressão inválida...'
        }
      } else {
        this.resultLabel = 'Expressão vazia...'
      }
    }
  }
}
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

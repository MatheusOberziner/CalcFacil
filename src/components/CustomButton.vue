<template>
  <div class="q-pb-xs" :class="button.class" style="height: 5em;">
    <q-btn
      no-caps
      :color="button.color"
      :label="button.label"
      :icon-right="button.icon"
      :style="button.style"
      style="width: 100%; height: 100%;"
      @click="handleButtonClick"
    />
  </div>
</template>
<script>
export default {
  name: 'CustomButton',
  props: {
    button: {
      type: Object,
      required: true
    }
  },
  methods: {
    handleButtonClick () {
      this.button.clickHandler()
    }
  }
}
</script>

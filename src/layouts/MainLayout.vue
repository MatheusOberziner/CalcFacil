<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated style="height: 10vh;">
      <q-toolbar class="row justify-between bg-white" style="height: 100%;">
        <div class="row items-center" :class="!$q.screen.lt.sm && 'q-gutter-md'">
          <q-avatar class="bg-primary" :class="$q.screen.lt.sm && 'q-mr-sm'"
            :style="$q.screen.lt.sm ? 'height: 1.3em; width: 1.3em;' : 'height: 1.7em; width: 1.7em;'">
            <q-img src="../assets/logo.svg" style="height: 70%; width: 70%;" />
          </q-avatar>

          <span class="text-primary text-bold" :class="$q.screen.lt.sm ? 'text-h4' : 'text-h3'">CalcFácil</span>
        </div>

        <div class="row items-center">
          <q-btn outline color="primary" label="documentação" :style="$q.screen.lt.sm && 'width: 9em;'"
            @click="showDocumentation()" />
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <q-page>
        <router-view />
      </q-page>
    </q-page-container>
  </q-layout>
</template>
<script>
import DocumentationDialog from 'src/components/DocumentationDialog.vue'

export default {
  name: 'MainLayout',
  methods: {
    showDocumentation () {
      this.$q.dialog({
        component: DocumentationDialog,
        parent: this
      })
    }
  }
}
</script>

<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
        >
          <q-icon name="menu" />
        </q-btn>

        <q-toolbar-title>
          Mirafox Limited
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
      content-class="bg-grey-2"
      behavior="mobile"
    >
      <q-list>
        <q-item-label header>Links</q-item-label>
        <q-item clickable tag="a" target="_blank" href="https://mirafox.com/">
          <q-item-section avatar>
            <q-img src="https://mirafox.com/wp-content/themes/mirafox/assets/images/logo.jpg"></q-img>
          </q-item-section>
          <q-item-section>
            <q-item-label>Mirafox</q-item-label>
            <q-item-label caption>limited</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { openURL } from 'quasar'

export default {
  name: 'MyLayout',
  data () {
    return {
      leftDrawerOpen: this.$q.platform.is.desktop
    }
  },
  methods: {
    openURL
  }
}
</script>

<style>
</style>

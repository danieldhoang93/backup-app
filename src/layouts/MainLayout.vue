<template>
  <q-layout view="hHh lpr fFf">
    <q-header reveal>
      <q-toolbar class="navbarWidth">
        <!--<q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />-->

        <q-toolbar-title class="headerSubText">
          DDH
        </q-toolbar-title>

        <!--
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="right = !right"
          style="z-index:9999;"/>
          -->
          <q-btn label="Sign Up" no-caps class="blueButton text-white" @click="signUp = true" />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="right"
      side="right"
      :breakpoint="767"
      :width="200"
      behavior="desktop"
      overlay
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <div class= "footer">
      
    </div>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      right: false,
      signUp: false,
      essentialLinks: linksData
    }
  }
}
</script>

<style lang="scss">
.q-header {
  background:rgba(0, 0, 0, 0);
  height:80px;
  display: flex;
  align-items: center;
  overflow-x:hidden;
  left:16px;
}
</style>
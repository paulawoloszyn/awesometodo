<template>
  <q-layout view="hhh lpR fFf">
    <q-header elevated>
      <q-toolbar>

        <q-toolbar-title class="absolute-center"> 
          Awesome To Do
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-footer>
        <q-tabs>
        <q-route-tab
        to="/"
        icon="playlist_add_check"
        label="To Do" />
        <q-route-tab 
        to="/settings"        
        icon="settings" 
        label="Settings" />
      </q-tabs>
      </q-footer>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-primary"
      :breakpoint="767"
      :width="250"
    >
      <q-list dark>
        <q-item-label
          header
          class="text-white"
        >
          Menú
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
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink'

export default {
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: [
        {
          title: 'To do',
          caption: '',
          icon: 'playlist_add_check',
          link:"/"
        },

        {
          title: 'Settings',
          caption: '',
          icon: 'settings',
          link:"/#/settings"
        }
      ]
    }
  }
}
</script>

<style lang="scss">
  @media screen and (min-width: 768px){
    .q-footer {
      display: none;
    }
  }


</style>
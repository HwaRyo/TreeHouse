<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title @click="goHome">
          TreeHouse
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
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
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'
import routes from 'src/router/routes'

const linksList = [
  {
    title: '홈',
    caption: 'Home',
    icon: 'school',
    link: '/'
  },
  {
    title: '공지사항',
    caption: 'Notice',
    icon: 'school',
    link: '/Notice'
  },
  {
    title: '이벤트',
    caption: 'Event',
    icon: 'code',
    link: '/Event'
  },
  {
    title: '보드게임',
    caption: 'Board Games',
    icon: 'chat',
    link: '/BoardGame'
  },
  {
    title: '예약',
    caption: 'Reservation',
    icon: 'record_voice_over',
    link: '/Reservation'
  },
  {
    title: '기록',
    caption: 'Record',
    icon: 'rss_feed',
    link: '/Record'
  }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },
      goHome () {
        routes.push('/')
      }
    }
  }
})
</script>

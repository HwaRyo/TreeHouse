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

        <q-toolbar-title>
          <q-btn
          flat
          bold
          no-caps
          dense
          size="25px"
          @click=$router-link to="/"
          >
          TreeHouse
        </q-btn>

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
          메뉴
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

      <q-footer elevated class="bg-white text-primary">
        <a>트리하우스보드게임카페<br/>위치 : 충청남도 천안시 서북구 쌍용17길 60-6 1층 <br/> 연락처 : 041-414-1777 <br /> 오픈채팅 : https://open.kakao.com/o/goH6V2dd</a>
      </q-footer>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: '홈',
    caption: 'Home',
    icon: 'home',
    link: '/'
  },
  {
    title: '공지사항',
    caption: 'Notice',
    icon: 'description',
    link: '/Notice'
  },
  {
    title: '이벤트',
    caption: 'Event',
    icon: 'event',
    link: '/Event'
  },
  {
    title: '보드게임',
    caption: 'Board Games',
    icon: 'casino',
    link: '/BoardGame'
  },
  {
    title: '예약',
    caption: '공사중',
    icon: 'calendar_month',
    link: '/Reservation'
  },
  {
    title: '기록',
    caption: 'Record',
    icon: 'view_list',
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
      }
    }
  }
})
</script>

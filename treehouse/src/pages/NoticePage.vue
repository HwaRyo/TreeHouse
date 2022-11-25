<template>
  <h4>공지사항</h4>
  <div>
    <q-card>
      <q-markup-table>
        <thead>
          <tr>
            <th>No.</th>
            <th>제목</th>
            <th>작성자</th>
            <th>작성일</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>06</td>
            <td>Frozen Yogurt</td>
            <td>159</td>
            <td>24</td>
          </tr>
        </tbody>
      </q-markup-table>
      <div class="q-pa-lg flex flex-center">
      <q-pagination
        v-model="current"
        :max="5"
        direction-links
      />
      </div>
    </q-card>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

// const NoticeList = [
//   {
//     title: '홈',
//     caption: 'Home',
//     icon: 'home',
//     link: '/'
//   },
//   {
//     title: '공지사항',
//     caption: 'Notice',
//     icon: 'description',
//     link: '/Notice'
//   },
//   {
//     title: '이벤트',
//     caption: 'Event',
//     icon: 'event',
//     link: '/Event'
//   },
//   {
//     title: '보드게임',
//     caption: 'Board Games',
//     icon: 'casino',
//     link: '/BoardGame'
//   },
//   {
//     title: '예약',
//     caption: 'Reservation',
//     icon: 'calendar_month',
//     link: '/Reservation'
//   },
//   {
//     title: '기록',
//     caption: 'Record',
//     icon: 'view_list',
//     link: '/Record'
//   }
// ]

export default defineComponent({
  name: 'EventPage'
})

</script>

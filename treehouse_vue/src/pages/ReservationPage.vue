<template>
  <h4>공사중</h4>
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
            <td>06</td>q
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

export default defineComponent({
  name: 'EventPage'
})
</script>

<template>
  <div class="q-pa-md">
    <q-carousel
      animated
      v-model="slide1"
      navigation
      infinite
      :autoplay="autoplay"
      arrows
      height="600px"
      transition-prev="slide-right"
      transition-next="slide-left"
      @mouseenter="autoplay = false"
      @mouseleave="autoplay = true"
    >
      <q-carousel-slide :name="1" img-src="https://cdn.quasar.dev/img/mountains.jpg" />
      <q-carousel-slide :name="2" img-src="https://cdn.quasar.dev/img/parallax1.jpg" />
      <q-carousel-slide :name="3" img-src="https://cdn.quasar.dev/img/parallax2.jpg" />
      <q-carousel-slide :name="4" img-src="https://cdn.quasar.dev/img/quasar.jpg" />
    </q-carousel>
  </div>

  <div class="midleContainer">
    <div class="notice">
      <h6>공지사항</h6>
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
            <tr>
              <td>06</td>
              <td>Frozen Yogurt</td>
              <td>159</td>
              <td>24</td>
            </tr>
            <tr>
              <td>06</td>
              <td>Frozen Yogurt</td>
              <td>159</td>
              <td>24</td>
            </tr>
            <tr>
              <td>06</td>
              <td>Frozen Yogurt</td>
              <td>159</td>
              <td>24</td>
            </tr>
            <tr>
              <td>06</td>
              <td>Frozen Yogurt</td>
              <td>159</td>
              <td>24</td>
            </tr>
          </tbody>
        </q-markup-table>
      </q-card>
    </div>
    <div class="record">
      <h6>작사 기록</h6>
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
      </q-card>
    </div>
  </div>

  <div class="q-pa-md">
    <q-carousel
      v-model="slide2"
      transition-prev="slide-right"
      transition-next="slide-left"
      swipeable
      animated
      control-color="primary"
      navigation
      padding
      arrows
      height="400px"
      class="bg-grey-1 shadow-2 rounded-borders"
    >
      <q-carousel-slide :name="1" class="column no-wrap">
        <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
          <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/mountains.jpg" />
          <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/parallax1.jpg" />
        </div>
      </q-carousel-slide>
      <q-carousel-slide :name="2" class="column no-wrap">
        <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
          <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/parallax2.jpg" />
          <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/quasar.jpg" />
        </div>
      </q-carousel-slide>
      <q-carousel-slide :name="3" class="column no-wrap">
        <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
          <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/cat.jpg" />
          <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/linux-avatar.png" />
        </div>
      </q-carousel-slide>
      <q-carousel-slide :name="4" class="column no-wrap">
        <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
          <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/material.png" />
          <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/donuts.png" />
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      slide1: ref(1),
      slide2: ref(1),
      autoplay: ref(true)
    }
  }
}
</script>

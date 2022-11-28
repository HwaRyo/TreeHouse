<template>
  <div class="q-pa-md">
    <q-date
      v-model="date"
    />
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  created () {
    this.today = new Date()
    this.todayString = this.today.getFullYear() + '/0' + (this.today.getMonth() + 1).slice(-2)
  },
  setup () {
    return {
      date: ref(null),
      today: '',
      todayString: ''
    }
  },
  methods: {
    test () {
    }
  }

}
</script>

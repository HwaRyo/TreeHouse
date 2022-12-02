=<template>
  <div class="q-pa-md">
    <h5>마작기록</h5>
    <div class="q-gutter-y-md column" style="max-width: 300px">
      <q-select color="purple-12" v-model="model" :options="options" label="일,월" :hint="dateString">
        <template v-slot:prepend>
          <q-icon name="event" />
        </template>
     </q-select>

    <div class="q-mb-sm">
      <q-badge color="teal">
        Model: {{ date }}
      </q-badge>
    </div>

     <div v-if="model=='일'" class="q-pa-md">
          <q-btn icon="event" round color="primary">
            <q-popup-proxy @before-show="updateProxy" cover transition-show="scale" transition-hide="scale">
              <q-date v-model="proxyDate" today-btn>
                <div class="row items-center justify-end q-gutter-sm">
                  <q-btn label="Cancel" color="primary" flat v-close-popup />
                  <q-btn label="OK" color="primary" flat @click="save" v-close-popup />
                </div>
              </q-date>
            </q-popup-proxy>
          </q-btn>
        </div>
    </div>

  </div>

  <div v-if="model=='일'" class="q-pa-md">
    <q-table
      :rows="rows"
      :columns="columns"
      row-key="name"
      rows-per-page-label="개수"
      :rows-per-page-options="[10, 20, 30, 40, 50, 0]"
    />
  </div>
</template>

<script>
import { ref } from 'vue'

const columns = [
  {
    name: 'name',
    required: true,
    label: '이름',
    align: 'left',
    field: row => row.name,
    format: val => `${val}`,
    sortable: true
  },
  { name: '국수', align: 'center', label: '국수', field: 'calories', sortable: true },
  { name: '1위', label: '1위', field: 'fat', sortable: true },
  { name: '2위', label: '2위', field: 'carbs', sortable: true },
  { name: '3위', label: '3위', field: 'protein', sortable: true },
  { name: '4위', label: '4위', field: 'sodium', sortable: true },
  { name: '총우마', label: '총우마', field: 'calcium', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
  { name: '평우마', label: '평우마', field: 'iron', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
  { name: '연대율', label: '연대율', field: 'sodium', sortable: true },
  { name: '라스율', label: '라스율', field: 'sodium', sortable: true }
]

const rows = [
  {
    name: 'Frozen Yogurt',
    calories: 159,
    fat: 6.0,
    carbs: 24,
    protein: 4.0,
    sodium: 87,
    calcium: '14%',
    iron: '1%'
  },
  {
    name: 'Frozen Yogurt',
    calories: 159,
    fat: 6.0,
    carbs: 24,
    protein: 4.0,
    sodium: 87,
    calcium: '14%',
    iron: '1%'
  },
  {
    name: 'Ice cream sandwich',
    calories: 237,
    fat: 9.0,
    carbs: 37,
    protein: 4.3,
    sodium: 129,
    calcium: '8%',
    iron: '1%'
  },
  {
    name: 'Eclair',
    calories: 262,
    fat: 16.0,
    carbs: 23,
    protein: 6.0,
    sodium: 337,
    calcium: '6%',
    iron: '7%'
  },
  {
    name: 'Cupcake',
    calories: 305,
    fat: 3.7,
    carbs: 67,
    protein: 4.3,
    sodium: 413,
    calcium: '3%',
    iron: '8%'
  },
  {
    name: 'Gingerbread',
    calories: 356,
    fat: 16.0,
    carbs: 49,
    protein: 3.9,
    sodium: 327,
    calcium: '7%',
    iron: '16%'
  },
  {
    name: 'Jelly bean',
    calories: 375,
    fat: 0.0,
    carbs: 94,
    protein: 0.0,
    sodium: 50,
    calcium: '0%',
    iron: '0%'
  },
  {
    name: 'Lollipop',
    calories: 392,
    fat: 0.2,
    carbs: 98,
    protein: 0,
    sodium: 38,
    calcium: '0%',
    iron: '2%'
  },
  {
    name: 'Honeycomb',
    calories: 408,
    fat: 3.2,
    carbs: 87,
    protein: 6.5,
    sodium: 562,
    calcium: '0%',
    iron: '45%'
  },
  {
    name: 'Donut',
    calories: 452,
    fat: 25.0,
    carbs: 51,
    protein: 4.9,
    sodium: 326,
    calcium: '2%',
    iron: '22%'
  },
  {
    name: 'KitKat',
    calories: 518,
    fat: 26.0,
    carbs: 65,
    protein: 7,
    sodium: 54,
    calcium: '12%',
    iron: '6%'
  }
]

export default {
  created () {
    this.today = new Date()
    this.year = this.today.getFullYear()
    this.month = ('0' + (this.today.getMonth() + 1)).slice(-2)
    this.day = ('0' + this.today.getDate()).slice(-2)
    this.dateString = '기준: ' + this.year + '-' + this.month + '-' + this.day
  },
  setup () {
    return {
      model: ref(null),
      columns,
      rows,
      check: false,
      selectLabel: '일',
      today: '',
      year: '',
      month: '',
      dateString: '',
      date: ref('2022/12/05'),
      proxyDate: ref('2022/12/05'),
      options: [
        '일', '월'
      ]
    }
  },
  methods: {
    updateProxy () {
      this.proxyDate = this.date
    },
    save () {
      this.date = this.proxyDate
      this.dateString = this.proxyDate
    }
  }

}
</script>

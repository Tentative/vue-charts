<template>
  <div>
    <topMenu></topMenu>
    <b-container v-if="indexes">
      <b-row>
        <b-col xs="12">
          <LineChart :indexes="indexes" :usd="usd"></LineChart>
        </b-col>
        <b-button @click="getData">Click</b-button>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import axios from 'axios'
import topMenu from '~/components/topMenu.vue'
import LineChart from '~/components/LineChart.vue'
export default {
  components: {
    topMenu,
    LineChart
  },
  data() {
    return {
      indexes: [],
      usd: {}
    }
  },
  created() {
    this.getData()
  },
  mounted() {
    this.getIndex()
  },
  methods: {
    async getData() {
      await axios
        .get('https://financialmodelingprep.com/api/v3/company/profile/USD')
        .then((res) => {
          // eslint-disable-next-line no-console
          console.log(res)
          this.usd = res.data.profile
          // eslint-disable-next-line no-console
          console.log(this.usd)
        })
    },
    getIndex() {
      for (let i = 0; i < 3; i++) {
        // eslint-disable-next-line no-console
        console.log('Block statement execution no.' + i)
      }
    }
  }
}
</script>

<style></style>

<template>
  <div>
    <topMenu></topMenu>
    <b-container v-if="examples">
      <b-row>
        <b-col xs="12">
          <LineChart :indexes="indexes" :bitcoin="bitcoin"></LineChart>
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
      bitcoin: []
    }
  },
  created() {
    this.getData()
  },
  methods: {
    async getData() {
      await axios.get('https://api.coinlore.com/api/tickers/').then((res) => {
        // eslint-disable-next-line no-console
        console.log(res)
        this.bitcoin = res.data.data
        // eslint-disable-next-line no-console
        console.log(this.bitcoin)
      })
    }
  }
}
</script>

<style></style>

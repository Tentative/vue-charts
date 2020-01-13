<template>
  <div>
    <topMenu></topMenu>
    <b-container>
      <b-row>
        <b-col xs="12">
          <LineChart :examples="examples" :test="test"></LineChart>
        </b-col>
        <b-button @click="getData">Click</b-button>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import topMenu from '~/components/topMenu.vue'
import LineChart from '~/components/LineChart.vue'
export default {
  components: {
    topMenu,
    LineChart
  },
  data() {
    return {
      test: {},
      examples: []
    }
  },
  mounted() {
    this.getData()
  },
  methods: {
    getData() {
      this.$axios.get('https://api.coinlore.com/api/tickers/').then((res) => {
        // eslint-disable-next-line no-console
        console.log(res)
        this.test = res
        this.examples = res.data.data
      })
    }
  }
}
</script>

<style></style>

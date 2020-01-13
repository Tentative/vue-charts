<template>
  <div>
    <topMenu></topMenu>
    <b-container>
      <b-row>
        <b-col xs="12">
          <LineChart></LineChart>
        </b-col>
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
      test: {}
    }
  },
  mounted() {
    this.getData()
  },
  methods: {
    getData() {
      this.$axios
        .get('http://www.omdbapi.com/?i=tt3896198&apikey=fc497c85')
        .then((res) => {
          this.console.log(res)
          this.test = res
        })
    }
  }
}
</script>

<style></style>

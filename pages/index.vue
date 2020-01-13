<template>
  <div>
    <topMenu></topMenu>
    <b-container fluid class="mt-1">
      <b-row>
        <b-col xs="12">
          <mainChart></mainChart>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import topMenu from '~/components/topMenu.vue'
import mainChart from '~/components/mainChart.vue'
export default {
  components: {
    topMenu,
    mainChart
  }
}
</script>

<style></style>

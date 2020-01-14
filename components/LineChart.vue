<script>
// Importing Line class from the vue-chartjs wrapper
import { Line, Bar } from 'vue-chartjs'

// Exporting this so it can be used in other components
export default {
  extends: Line,
  Bar,
  props: {
    usd: {
      type: Object,
      required: true
    },
    indexes: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      datacollection: {
        // Data to be represented on x-axis
        labels: ['Price A', 'Price B'],
        datasets: [
          {
            label: 'Data One',
            backgroundColor: '',
            pointBackgroundColor: 'white',
            borderWidth: 1,
            pointBorderColor: '#249EBF',
            // Data to be represented on y-axis
            data: [Math.floor(Math.random() * 9) + 1, 2, 3, 4, 5, 6, 7]
          },
          {
            label: 'Data Two',
            backgroundColor: '',
            pointBackgroundColor: 'white',
            borderWidth: 1,
            pointBorderColor: '#249EBF',
            // Data to be represented on y-axis
            data: [Math.floor(Math.random() * 9) + 1, 1, 3, 4]
          },
          {
            label: 'Data Two',
            backgroundColor: '',
            pointBackgroundColor: 'white',
            borderWidth: 1,
            pointBorderColor: '#249EBF',
            // Data to be represented on y-axis
            data: [Math.floor(Math.random() * 9) + 1, 1, 3, 4],
            type: 'bar'
          }
        ]
      },
      // Chart.js options that controls the appearance of the chart
      options: {
        scales: {
          yAxes: [
            {
              ticks: {
                beginAtZero: true
              },
              gridLines: {
                display: true
              }
            }
          ],
          xAxes: [
            {
              gridLines: {
                display: false
              }
            }
          ]
        },
        legend: {
          display: true
        },
        responsive: true,
        maintainAspectRatio: false
      }
    }
  },
  mounted() {
    // renderChart function renders the chart with the datacollection and options object.
    this.renderChart(this.datacollection, this.options)
  }
}
</script>

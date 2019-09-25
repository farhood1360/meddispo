<script>
import { Line } from 'vue-chartjs'
import { CustomTooltips } from '@coreui/coreui-plugin-chartjs-custom-tooltips'
import { hexToRgba } from '@coreui/coreui/dist/js/coreui-utilities'

export default {
  components: {
    hexToRgba,
    CustomTooltips
  },
  extends: Line,
  mounted () {
    this.renderChart(
      {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
        datasets: [
          {
            label: 'Zone 1',
            backgroundColor: hexToRgba('#E46651', 90),
            data: [30, 39, 10, 50, 30, 70, 35, 40, 50, 20, 10]
          },
          {
            label: 'Zone 2',
            backgroundColor: hexToRgba('#00D8FF', 90),
            data: [39, 80, 40, 35, 40, 20, 45, 20, 10, 30, 40]
          }
        ]
      },
      {
        responsive: true,
        maintainAspectRatio: true,
        tooltips: {
          enabled: false,
          custom: CustomTooltips,
          intersect: true,
          mode: 'index',
          position: 'nearest',
          callbacks: {
            labelColor: function (tooltipItem, chart) {
              return { backgroundColor: chart.data.datasets[tooltipItem.datasetIndex].backgroundColor }
            }
          }
        }
      }
    )
  }
}
</script>

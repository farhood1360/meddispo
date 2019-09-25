<script>
import { Pie } from 'vue-chartjs'

export default {
  extends: Pie,
  mounted () {
    this.renderChart({
      labels: ['Zone1', 'Zone2', 'Zone3', 'Zone4'],
      datasets: [
        {
          backgroundColor: [
            '#ccc',
            '#E46651',
            '#00D8FF',
            '#DD1B16'
          ],
          data: [100, 80, 200, 300]
        }
      ]
    }, {responsive: true, maintainAspectRatio: true})
  }
}
</script>

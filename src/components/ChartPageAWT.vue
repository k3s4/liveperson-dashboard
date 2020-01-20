<template>
  <mdb-container>
    <mdb-bar-chart :data="barChartData" :options="barChartOptions" :width="600" :height="300"></mdb-bar-chart>
  </mdb-container>
</template>

<script>
  import { mdbBarChart, mdbContainer } from 'mdbvue';
  export default {
    name: 'ChartPage',
    components: {
      mdbBarChart,
      mdbContainer
    },
    data() {
      return {
        barChartData: {
          labels: ["1435293450", "1435308550", "1435292750", "1435293450", "1412751950"],
          datasets: [{
            label: 'Avg Wait Time For Agent Assignment New Conversation',
            data: [14476220, 7680906, 19859075, 14488221, 6515862],
            backgroundColor: [
              'rgba(255, 99, 132, 0.2)',
              'rgba(54, 162, 235, 0.2)',
              'rgba(255, 206, 86, 0.2)',
              'rgba(75, 192, 192, 0.2)',
              'rgba(153, 102, 255, 0.2)',
              'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
              'rgba(255,99,132,1)',
              'rgba(54, 162, 235, 1)',
              'rgba(255, 206, 86, 1)',
              'rgba(75, 192, 192, 1)',
              'rgba(153, 102, 255, 1)',
              'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1,
          }]
        },
        barChartOptions: {
          responsive: true,
          maintainAspectRatio: false,
          scales: {
            xAxes: [{
              barPercentage: 1,
              gridLines: {
                display: true,
                color: "rgba(0, 0, 0, 0.1)"
              }
            }],
            yAxes: [{
              gridLines: {
                display: true,
                color: "rgba(0, 0, 0, 0.1)"
              }
            }]
          }
        }
      };
    }
  }
</script>

<template>
  <mdb-container>
    <mdb-horizontal-bar-chart
      :data="barChartData"
      :options="barChartOptions"
     ></mdb-horizontal-bar-chart>
  </mdb-container>
</template>

<script>
/* eslint-disable no-console */
import { mdbHorizontalBarChart, mdbContainer } from "mdbvue";
export default {
  name: "ChartPage",
  components: {
    mdbHorizontalBarChart,
    mdbContainer
  },
  
  data() {
    return {
      barChartData: {
        labels: [],
        datasets: []
      },
      barChartOptions: {
	animation: {
		duration: 0
	},
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          xAxes: [
            {
              barPercentage: 1,
              gridLines: {
                display: true,
                color: "rgba(0, 0, 0, 0.1)"
              }
            }
          ],
          yAxes: [
            {
              gridLines: {
                display: true,
                color: "rgba(0, 0, 0, 0.1)"
              }
            }
          ]
        }
      }
    };
  },
  methods: {
	requestdata: function () {
		fetch("https://magenta-json.herokuapp.com")
		.then(res => res.json())
		.then(json => {
        var name = [];
		var unassignedConversations = [];
		
		for(var i = 0; i < json.rows.length; i++) {
			name.push(json.rows[i].name);
			unassignedConversations.push(json.rows[i].unassignedConversations);
		}

        const dataset = {
          label: "Unassigned Conversations",
          data: unassignedConversations,
          borderWidth: 1
        };
        this.barChartData = {
          ...this.barChartData,
          labels: name,
          datasets: [dataset]
        };
      });
  }
  },
  mounted() {
    this.requestdata();
	setInterval(() => {
		this.requestdata();
	}, 5000)
  }
};
</script>

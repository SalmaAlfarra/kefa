<template>
  <div>
    <v-card min-height="23vh" class="mt-7 d-flex flex-column justify-start">
      <v-toolbar flat class="w-100">
        <v-list-item two-line class="text-right">
          <v-list-item-content>
            <v-list-item-title> مؤشر أداء الكاشير</v-list-item-title>
            <v-list-item-subtitle> </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-spacer></v-spacer>
      </v-toolbar>
      <apexchart
        type="rangeBar"
        height="90%"
        max-width="100%"
        :options="chartOptions"
        :series="series"
        class="mx-auto w-100"
      ></apexchart>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      series: [
        {
          type: "rangeBar",
          data: [
            {
              x: "2008",
              y: [2800, 4500],
            },
            {
              x: "2009",
              y: [3200, 4100],
            },
            {
              x: "2010",
              y: [2950, 7800],
            },
            {
              x: "2011",
              y: [3000, 4600],
            },
            {
              x: "2012",
              y: [3500, 4100],
            },
            {
              x: "2013",
              y: [4500, 6500],
            },
            {
              x: "2014",
              y: [4100, 5600],
            },
          ],
        },
       
      ],
      chartOptions: {
        chart: {
          height: 350,
          type: "rangeBar",
          zoom: {
            enabled: false,
          },
        },
        plotOptions: {
          bar: {
            isDumbbell: true,
            columnWidth: 3,
            dumbbellColors: [["#008FFB", "#00E396"]],
          },
        },
        legend: {
          show: true,
          showForSingleSeries: true,
          position: "bottom",
          horizontalAlign: "center",
          customLegendItems: ["المبيعات", "الطلبات", "المرتجع", "الملغي"],
          markers: {
            fillColors: ["#0AB39C", "#F2EDEE", "#405189"],
          },
        },
        fill: {
          type: "gradient",
          gradient: {
            type: "vertical",
            gradientToColors: ["#00E396"],
            inverseColors: true,
            stops: [0, 100],
          },
        },
        grid: {
          xaxis: {
            lines: {
              show: true,
            },
          },
          yaxis: {
            lines: {
              show: false,
            },
          },
        },
        xaxis: {
          tickPlacement: "on",
        },
      },
    };
  },
};
</script>

<style>
</style>
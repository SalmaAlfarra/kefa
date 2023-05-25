<template>
  <div>
    <v-card min-height="23vh" class="mt-5 d-flex flex-column justify-start">
      <v-toolbar flat class="w-100">
        <v-list-item two-line class="text-right">
          <v-list-item-content>
            <v-list-item-title> مؤشر أداء المبيعات</v-list-item-title>
            <v-list-item-subtitle>
              
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-spacer></v-spacer>
        <!-- <v-btn
          icon
          tile
          color="#778CA2"
          v-for="i in 3"
          :key="i"
          class="text-center mr-2 ml-2"
        >
          <h5 class="w-100">
            {{ i }}
          </h5>
        </v-btn> -->
      </v-toolbar>
      <apexchart
        type="donut"
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
      series: [44, 55, 41, 17],
      chartOptions: {
        chart: {
          type: "donut",
           width: 500,
        },
        fill: { colors: ["#405189", "#F06548", "#F7B84B", "#0AB39C"] },

        legend: {
          position: "bottom",
           customLegendItems: [
            "المبيعات",
            "الطلبات",
            "المرتجع",
            "الملغي",
          ],
          markers: {
            fillColors: ["#0AB39C", "#F2EDEE", "#405189"],
          },
        },
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 200,
              },
              legend: {
                position: "bottom",
              },
            },
          },
        ],
      },
    };
  },
};
</script>

<style>
</style>
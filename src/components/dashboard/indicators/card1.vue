<template>
  <div>
    <v-card
      min-height="50vh"
      max-width="100vw"
      class="mt-5"
      style="oveflow: auto"
    >
      <v-toolbar flat>
        <v-list-item two-line class="text-right">
          <v-list-item-content>
            <v-list-item-title>احصائيات الارباح</v-list-item-title>
            <v-list-item-subtitle>
              شاهد تحليلات واحصائيات الأرباح والمرتجعات
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-spacer></v-spacer>
        <div v-if="!hide_btns" class="d-flex">
          <v-btn
            icon
            tile
            color="#778CA2"
            class="text-center mr-2 ml-2 d-flex flex-column"
            v-for="(btn, i) in btns"
            :key="i"
          >
            <h5 class="w-100">{{ btn.title }}</h5>
            <br />
            <h5 class="w-100">
              {{ btn.subtitle }}
            </h5>
          </v-btn>
        </div>
      </v-toolbar>

      <apexchart
        width="100%"
        height="100%"
        max-height="100%"
        type="bar"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "bar-chart",
  data() {
    return {
      chartOptions: {
        colors: ["#013467"],
        chart: {
          height: 350,
          width: 10,
          type: "line",
        },
        stroke: {
          width: [0, 1],
          curve: "smooth",
        },
        fill: {
          type: "solid",
          opacity: [0.9, 0.35],
        },
        xaxis: {
          categories: [
            "ديسمبر",
            "نوفمبر",
            "أكتوبر",
            "سبتمبر",
            "اغسطس",
            "يوليو",
            "يونيو",
            "مايو",
            "أبريل",
            "مارس",
            "فبراير",
            "يناير",
          ],
        },
        // xaxis: {
        //   labels: {
        //     style: {
        //     },

        //   },
        // },
        legend: {
          show: true,
          showForSingleSeries: true,
          customLegendItems: [
            "إجمالي الأرباح",
            "اجمالي المرتجعات",
            "اجمالي الفواتير الأجلة",
          ],
          markers: {
            fillColors: ["#0AB39C", "#F2EDEE", "#405189"],
          },
        },
      },
      series: [
        {
          name: "Website Blog",
          type: "column",
          data: [440, 505, 414, 671, 227, 413, 201, 352, 752, 320, 257, 160],
        },
        {
          name: "Social Media",
          type: "area",
          data: [350, 480, 313, 650, 310, 450, 380, 170, 700, 580, 322, 122],
        },
      ],

      btns: [
        {
          title: "الكل",
          subtitle: "",
        },
        {
          title: "1",
          subtitle: "شهر",
        },
        {
          title: "6",
          subtitle: "شهر",
        },
        {
          title: "1",
          subtitle: "سنة",
        },
      ],
    };
  },
  computed: {
    hide_btns() {
      return this.$vuetify.breakpoint.name == "xs" ||
        this.$vuetify.breakpoint.name == "sm"
        ? true
        : false;
    },
  },
};
</script>

<style>
</style>
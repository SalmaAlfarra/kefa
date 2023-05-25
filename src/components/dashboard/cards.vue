<template>
  <v-row class="mt-3 pl-4 pr-5">
    <v-col
      cols="12"
      xl="3"
      lg="3"
      md="3"
      sm="12"
      v-for="(card, i) in cards"
      :key="i"
      class=""
    >
      <v-card elevation="5">
        <v-toolbar color="white" flat>
          <h4 class="pr-4 pl-4">{{ card.title }}</h4>
          <v-spacer></v-spacer>
          <div class="green--text"> <v-icon>mdi-trending-up</v-icon> {{ card.indicator }}</div>
        </v-toolbar>
        <v-card-text>
          <div class="d-flex pa-0 ">
            <v-col cols="6" class="text-right">
              <h4 class="mb-3">{{ card.price }}</h4>
              <router-link class="blue--text" to="/"
                ><b>شاهد التفاصيل</b></router-link
              >
            </v-col>
            <v-btn fab x-small tile :color="card.color" class="mt-8 rounded-lg mr-auto">
              <img :src="card.img" alt="" />
            </v-btn>
          </div>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "dashboard-cards",
  data() {
    return {
      cards: [
        {
          title: "إجمالي المبيعات",
          indicator: "+18.26 %",
          price: "1586.26 س.ر",
          img: require("@/assets/icons/money-send.png"),
          color: "#D3F1ED"
        },
        {
          title: "إجمالي ضريبة المبيعات",
          indicator: "+18.26 %",
          price: "1586.26 س.ر",
          img: require("@/assets/icons/vuesax-linear-dollar-circle.png"),
          color: "#D8EDF9"
        },
        {
          title: "إجمالي المشتريات",
          indicator: "+18.26 %",
          price: "1586.26 س.ر",
          img: require("@/assets/icons/money-recive.png"),
          color: "#FEF2DF"
        },
        {
          title: "إجمالي ضريبة المبيعات",
          indicator: "+18.26 %",
          price: "1586.26 س.ر",
          img: require("@/assets/icons/discount-circle.png"),
          color: "#DDE0EA"
        },
      ],
    };
  },
};
</script>

<style>
</style>
<template>
  <v-row class="pt-0">
    <v-col cols="12">
      <dashboardHeader />
    </v-col>
    <v-col cols="12">
      <dashboardCards />
    </v-col>

    <!--  indicators & charts -->
    <v-row class="pr-8 pl-7">
      <v-col cols="12" xl="8" lg="8" md="8" sm="12">
        <card1 />
      </v-col>
      <v-col cols="12" xl="4" lg="4" md="4" sm="12">
        <card2 />
        <card3 />
      </v-col>
    </v-row>

    <v-row class="pr-8 pl-7 mt-3 w-100">
      <v-col cols="12" xl="7" lg="7" md="7" sm="12">
        <bestSeller />
      </v-col>
      <v-col cols="12" xl="5" lg="5" md="5" sm="12">
        <leastOrder />
        <leastSelling class="mt-3"/>
      </v-col>
    </v-row>

    <v-row class="pr-8 pl-7 mt-3 w-100">
      <v-col cols="12" xl="6" lg="6" md="6" sm="12">
        <almostSold />
      </v-col>
      <v-col cols="12" xl="6" lg="6" md="6" sm="12">
        <almostSold />
      </v-col>
    </v-row>
  </v-row>
</template>

<script>
import dashboardHeader from "@/components/dashboard/headers.vue";
import dashboardCards from "@/components/dashboard/cards.vue";

//indicators and charts components
import card1 from "../components/dashboard/indicators/card1.vue";
import card2 from "../components/dashboard/indicators/card2.vue";
import card3 from "../components/dashboard/indicators/card3.vue";

//products sales tables
import bestSeller from "../components/dashboard/tables/bestSeller.vue";
import leastOrder from "../components/dashboard/tables/leastOrder.vue";
import leastSelling from "../components/dashboard/tables/leastSelling.vue";
import almostExpired from '../components/dashboard/tables/almostExpired.vue';
import almostSold from '../components/dashboard/tables/almostSold.vue';

export default {
  name: "dashboard-view",
  components: {
    dashboardHeader,
    dashboardCards,
    card1,
    card2,
    card3,

    //
    bestSeller,
    leastOrder,
    leastSelling,
    almostExpired,
    almostSold

  },
};
</script>

<style>
.w-100 {
  width: 100%;
}
</style>
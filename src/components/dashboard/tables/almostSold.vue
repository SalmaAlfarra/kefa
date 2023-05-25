<template>
  <v-card max-height="55vh" height="fit-content">
    <v-toolbar flat>
      <v-list-item two-line class="text-right">
        <v-list-item-content>
          <v-list-item-title
            >منتجات قاربت على انتهاء المخزون
          </v-list-item-title>
          <v-list-item-subtitle>
            شاهد تحليلات واحصائيات الأرباح والمرتجعات
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-data-table
      hide-default-header
      hide-default-footer
      :headers="headers"
      :items="desserts"
      flat
    >
      <template v-slot:item.img="{ item }">
        <v-avatar size="" tile>
          <img :src="item.img" alt="" />
        </v-avatar>
      </template>
      <template v-slot:item.name="{ item }">
        <v-list-item two-line class="text-right">
          <v-list-item-content>
            <v-list-item-title>{{ item.name.title }}</v-list-item-title>
            <v-list-item-subtitle>
              {{ item.name.subtitle }}
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>
      <template v-slot:item.price="{ item }">
        <v-list-item two-line class="text-right">
          <v-list-item-content>
            <v-list-item-title>{{ item.price.title }}</v-list-item-title>
            <v-list-item-subtitle>
              {{ item.price.subtitle }}
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>
      <template v-slot:item.qty="{ item }">
        <v-list-item two-line class="text-right">
          <v-list-item-content>
            <v-list-item-title>{{ item.qty.title }}</v-list-item-title>
            <v-list-item-subtitle>
              {{ item.qty.subtitle }}
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>
      <template v-slot:item.sold_qty="{ item }">
        <v-list-item two-line class="text-right">
          <v-list-item-content>
            <v-list-item-title>{{ item.sold_qty.title }}</v-list-item-title>
            <v-list-item-subtitle>
              {{ item.sold_qty.subtitle }}
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>

      <template v-slot:item.actions="{ item }">
        <v-btn color="#D8EDF9" class="blue--text" dense small>تعديل</v-btn>
      </template>
    </v-data-table>
    <div class="text-center d-flex w-100 mt-13">
      <v-pagination v-model="page" :length="3" class="mr-auto"></v-pagination>
    </div>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        {
          text: "img",
          align: "start",
          sortable: false,
          value: "img",
        },
        { text: "name", value: "name" },
        { text: "price", value: "price" },
        { text: "Carbs (g)", value: "qty" },
        { text: "Protein (g)", value: "sold_qty" },
        { text: "Iron (%)", value: "actions" },
      ],
      desserts: [
        {
          img: require("@/assets/img/products/product10.png"),
          name: {
            title: "صناديق المياه",
            subtitle: "ماركة فلو",
          },
          price: {
            title: "15 رس",
            subtitle: "السعر للوحدة",
          },
          qty: {
            title: "1563",
            subtitle: "الكمية المتوفرة",
          },
          sold_qty: {
            title: "4060",
            subtitle: "الكمية المباعة",
          },
        },
        {
          img: require("@/assets/img/products/product11.png"),
          name: {
            title: "صناديق المياه",
            subtitle: "ماركة فلو",
          },
          price: {
            title: "15 رس",
            subtitle: "السعر للوحدة",
          },
          qty: {
            title: "1563",
            subtitle: "الكمية المتوفرة",
          },
          sold_qty: {
            title: "4060",
            subtitle: "الكمية المباعة",
          },
        },
        {
          img: require("@/assets/img/products/product12.png"),
          name: {
            title: "صناديق المياه",
            subtitle: "ماركة فلو",
          },
          price: {
            title: "15 رس",
            subtitle: "السعر للوحدة",
          },
          qty: {
            title: "1563",
            subtitle: "الكمية المتوفرة",
          },
          sold_qty: {
            title: "4060",
            subtitle: "الكمية المباعة",
          },
        },
        {
          img: require("@/assets/img/products/product13.png"),
          name: {
            title: "صناديق المياه",
            subtitle: "ماركة فلو",
          },
          price: {
            title: "15 رس",
            subtitle: "السعر للوحدة",
          },
          qty: {
            title: "1563",
            subtitle: "الكمية المتوفرة",
          },
          sold_qty: {
            title: "4060",
            subtitle: "الكمية المباعة",
          },
        },
      ],
    };
  },
  methods: {
    getColor(calories) {
      if (calories > 400) return "red";
      else if (calories > 200) return "orange";
      else return "green";
    },
  },
};
</script>

<style>
</style>
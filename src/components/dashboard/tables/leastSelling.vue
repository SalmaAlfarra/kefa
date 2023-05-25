<template>
  <v-card max-height="27vh" height="fit-content">
    <v-toolbar flat>
      <v-list-item two-line class="text-right">
        <v-list-item-content>
          <v-list-item-title>المنتجات الأقل مبيعاً</v-list-item-title>
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

      <template v-slot:item.actions="{ item }">
        <v-btn color="#D8EDF9" class="blue--text" dense small>تعديل</v-btn>
      </template>
    </v-data-table>
    <div class="text-center d-flex w-100">
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

        { text: "Iron (%)", value: "actions" },
      ],
      desserts: [
        {
          img: require("@/assets/img/products/product8.png"),
          name: {
            title: "خردل اصفر",
            subtitle: "ماركة هاينز",
          },
          price: {
            title: "15 رس",
            subtitle: "السعر للوحدة",
          },
          qty: {
            title: "1563",
            subtitle: "الكمية المتوفرة",
          },
        },
        {
          img: require("@/assets/img/products/product9.png"),
          name: {
            title: "شوكلاته نوتيلا",
            subtitle: "ماركة نوتيلا",
          },
          price: {
            title: "15 رس",
            subtitle: "السعر للوحدة",
          },
          qty: {
            title: "1563",
            subtitle: "الكمية المتوفرة",
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
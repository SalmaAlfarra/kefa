<template>
  <v-toolbar color="#F6F8F9" flat>
    <v-toolbar-title>
      <v-list-item two-line class="text-right">
        <v-list-item-content>
          <v-list-item-title> صباح الخير , أحمد </v-list-item-title>
          <v-list-item-subtitle>
            تابع جميع نشاطاتك واحصائيات من خلال التالي
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn elevation="5" class="add-new-product"
      ><v-icon class="ml-2">mdi-package-variant</v-icon> إضافة منتج جديد</v-btn
    >
  </v-toolbar>
</template>

<script>
export default {};
</script>

<style>
.add-new-product {
  background-color: #d3f1ed !important;
  color: #0ab39c !important;
}
</style>
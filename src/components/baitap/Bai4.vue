<template>
  <h3>Bài tập 4 :</h3>
  <div class="d-flex justify-space-around">
    <v-menu>
      <template v-slot:activator="{ props }">
        <v-btn color="primary" v-bind="props"> QUẢN TRỊ VIÊN </v-btn>
      </template>
      <v-list>
        <v-list-item v-for="(item, index) in items" :key="index" :value="index">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const items = reactive([
  { title: "Thông tin cá nhân" },
  { title: "Đổi mật khẩu" },
  { title: "Đăng xuất" },
]);
</script>

<style></style>

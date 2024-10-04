<template>
  <div>
    <h3>Bài tập 7 :</h3>
    <v-pagination v-model="page" :length="4" rounded="circle"></v-pagination>

    <v-pagination v-model="page" :length="4" rounded="0"></v-pagination>
  </div>
</template>

<script setup>
import { ref } from "vue";

const page = ref(1);
</script>

<style></style>

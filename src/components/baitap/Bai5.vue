<template>
  <div>
    <h1>Bài tập 5 :</h1>
    <v-alert
      v-model="alert"
      title="Xác nhận"
      variant="tonal"
      closable
      style="max-width: 500px"
      class="mx-auto"
    >
      Bạn có chắn chắn muốn xóa tài khoản này không ?
    </v-alert>
  </div>
</template>
<script></script>

<style scoped>
.modal {
  width: 500px;
  margin: auto;
}
</style>

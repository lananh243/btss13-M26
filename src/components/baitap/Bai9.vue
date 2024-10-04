<template>
  <h3>Bài tập 9</h3>
  <div class="container">
    <div>
      <form @submit.prevent="v$.$validate" style="max-width: 500px">
        <v-toolbar cards dark flat>
          <v-card-title class="text-h6 font-weight-regular">
            Basic Layout
          </v-card-title>
        </v-toolbar>
        <v-text-field label="Name" required></v-text-field>
        <v-text-field label="Company" required></v-text-field>
        <v-text-field label="E-mail" required></v-text-field>

        <v-text-field label="Phone No" required></v-text-field>
        <v-textarea
          v-model="bio"
          color="deep-purple"
          label="Message"
          rows="1"
          variant="filled"
          auto-grow
        ></v-textarea>
        <v-btn type="submit" class="me-4" color="blue">Submit</v-btn>
      </form>
    </div>
    <p>
      ---------------------------------------------------------------------------------------------------------------
    </p>
    <div>
      <form @submit.prevent="v$.$validate" style="max-width: 500px">
        <v-toolbar cards dark flat>
          <v-card-title class="text-h6 font-weight-regular">
            Basic with icons
          </v-card-title>
        </v-toolbar>
        <v-text-field label="Name" required>
          <template v-slot:prepend-inner>
            <i class="fa-solid fa-user"></i>
          </template>
        </v-text-field>

        <v-text-field label="Company" required
          ><template v-slot:prepend-inner>
            <i class="fa-solid fa-building"></i> </template
        ></v-text-field>
        <v-text-field label="E-mail" required>
          <template v-slot:prepend-inner>
            <i class="fa-regular fa-envelope"></i>
          </template>
        </v-text-field>

        <v-text-field label="Phone No" required>
          <template v-slot:prepend-inner>
            <i class="fa-solid fa-phone"></i>
          </template>
        </v-text-field>
        <v-textarea
          v-model="bio"
          color="deep-purple"
          label="Message"
          rows="1"
          variant="filled"
          auto-grow
        >
          <template v-slot:prepend-inner>
            <i class="fa-regular fa-message"></i>
          </template>
        </v-textarea>
        <v-btn type="submit" class="me-4" color="blue">Submit</v-btn>
      </form>
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";
import { useVuelidate } from "@vuelidate/core";
import { email, required } from "@vuelidate/validators";

const initialState = {
  name: "",
  email: "",
  phone: "",
  message: "",
  select: null,
  checkbox: false, // Đảm bảo checkbox có giá trị khởi tạo
};

const state = reactive({
  ...initialState,
});

const rules = {
  name: { required },
  email: { required, email },
  phone: { required },
  message: { required },
  checkbox: { required },
};

const v$ = useVuelidate(rules, state);
</script>

<style scoped></style>

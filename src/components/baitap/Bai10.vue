<template>
  <h3>Bài tập 10 :</h3>
  <v-data-table :headers="headers" :items="vegetables">
    <template v-slot:top>
      <v-toolbar flat>
        <v-toolbar-title>Item</v-toolbar-title>
      </v-toolbar>
    </template>
    <template v-slot:item.status="{ value }">
      <v-chip :color="getColor(value)">
        {{ value }}
      </v-chip>
    </template>
  </v-data-table>
</template>

<script>
export default {
  data: () => ({
    headers: [
      { title: "Name", key: "name" },
      { title: "Project Name", key: "projectName" },
      { title: "Post", key: "post" },
      { title: "Status", key: "status" },
      { title: "Budget", key: "budget" },
    ],
    vegetables: [
      {
        name: "Sunil Joshi",
        status: "Active",
        post: "Web Designer",
        projectName: "Elite Admin",
        budget: "$3.9",
      },
      {
        name: "Andrew McDownland",
        status: "Pending",
        post: "Project Manager",
        projectName: "Real Homes WP Theme",
        budget: "$24.5k",
      },
      {
        name: "Christopher Jamil",
        status: "Completed",
        post: "Project Manager",
        projectName: "MedicalPro WP Theme",
        budget: "$12.8k",
      },
      {
        name: "Micheal Doe",
        status: "Active",
        post: "Fronted Engineer",
        projectName: "Hosting Press HTML",
        budget: "$2.4k",
      },
      {
        name: "Avocado",
        status: "Cancel",
        post: "Content Writer",
        projectName: "Helping Hands WP Theme",
        budget: "$9.3k",
      },
    ],
  }),

  methods: {
    getColor(status) {
      if (status === "Cancel") return "red";
      else if (status === "Pending") return "orange";
      else if (status === "Completed") return "blue";
      else return "green";
    },
  },
};
</script>

<style></style>

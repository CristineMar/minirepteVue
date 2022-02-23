<template>
  <!-- <div class="container">
    <table class="table mt-5">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Competències tècniques</th>
          <th scope="col">Nivel</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(allData, i) in allDatas" :key="i">
          <th scope="row">{{ ++i }}</th>
          <td>{{ allData.compTec}}</td>
          <td>{{ allData.level }}</td>
        </tr>
      </tbody>
    </table>
  </div>
 -->
  <div class="container">
    <v-card>
      <v-card-title>
        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="Search"
          single-line
          hide-details
        ></v-text-field>
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="allDatas"
        :search="search"
      ></v-data-table>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "Leaderboard",
  data() {
    return {
      search: "",
      headers: [
        {
          text: "Competències tècniques",
          align: "start",
          filterable: true,
          value: "compTec",
        },
        {
          text: "Nivel",
          align: "start",
          filterable: true,
          value: "level",
        },
      ],
    };
  },

  props: ["allDatas"],
};
</script>
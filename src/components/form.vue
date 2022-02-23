<template>
  <div class="container">
    <h1 class="mt-4 text-center">Llista de Competències tècniques</h1>
    <v-form ref="form" v-model="valid" lazy-validation>
      <v-text-field
        v-model="compTec"
        :counter="50"
        :rules="compTecRules"
        label="Competències tècniques"
        required
      ></v-text-field>

      <v-text-field
        v-model="level"
        :counter="20"
        :rules="levelRules"
        label="Nivell"
        required
      ></v-text-field>

      <v-btn :disabled="!valid" color="success" class="mr-4" @click="onSubmit">
        Submit
      </v-btn>
      <v-btn color="error" class="mr-4" @click="clearForm"> Reset Form </v-btn>
      <v-btn color="warning" @click="resetValidation"> Reset Validation </v-btn>
    </v-form>

    <app-tablelist :allDatas="allDatas"></app-tablelist>
  </div>
</template>

<script>
import tableListVue from "./tableList.vue";

export default {
  name: "LeaderboardForm",
  components: { "app-tablelist": tableListVue },
  data: () => ({
    valid: true,
    compTec: "",
        compTecRules: [
      (v) => !!v || "Competències tècniques is required",
      (v) => (v && v.length <= 50) || "Competències tècniques must be less than 50 characters",
    ],
    level: "",
    levelRules: [
      (v) => !!v || "Level is required",
      (v) => (v && v.length <= 20) || "Level must be less than 20 characters",
    ],
    allDatas: [],
  }),
  methods: {
    onSubmit() {
      let con = this.$refs.form.validate()

      if (con == true) {
              this.allDatas.push({ compTec: this.compTec, level: this.level });
              this.clearForm();
              this.resetValidation();
      }
    },
    clearForm() {
      this.compTec = "";
      this.level = "";
      this.resetValidation();
    },
    resetValidation () {
        this.$refs.form.resetValidation()
      },
  },
};
</script>

<style>
.container {
  height: 100%;
}
</style>
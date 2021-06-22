<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center">
        <logo />
        <vuetify-logo />
      </div>
    </v-col>
    <v-col cols="12" sm="8" md="10">
      <v-card md="8">
        <v-card-title>
          <h3>Welcome to the Vuetify + Nuxt.js Data Table Projects</h3>
        </v-card-title>
        <v-card-text>
          <h4>
            in this data table i used pagination to change path api Iran -
            tehran 22/6/2021
          </h4>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn color="primary" nuxt to="/Table"> Continue </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";
export default {
  components: {
    Logo,
    VuetifyLogo,
  },
};
</script>

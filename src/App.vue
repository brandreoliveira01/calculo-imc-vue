<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <v-spacer></v-spacer>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="./assets/logo.png"
          transition="scale-transition"
          width="40"
        />
        <h2 class="headline font-weight-bold mb-3">
          Cálculo IMC - Vue
        </h2>
      </div>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <CalculateIMC/>
    </v-main>
  </v-app>
</template>

<script>
import CalculateIMC from './components/CalculateIMC';

export default {
  name: 'App',

  components: {
    CalculateIMC,
  },

  data: () => ({
    //
  }),
};
</script>

<template>
  <v-container>
    <v-row dense class="mt-6">
      <v-col cols="12">
        <v-card max-width="380" class="mx-auto" elevation="6">
          <v-row justify="center">
            <v-col class="mt-5" cols="12" sm="8">
              <v-text-field
                autofocus
                outlined
                dense
                label="Altura"
                type="number"
                step="0.01"
                min="0"
                v-model="height"
                suffix="m"
              ></v-text-field>
              <v-text-field
                outlined
                dense
                label="Peso"
                type="number"
                min="0"
                v-model="weight"
                suffix="kg"
              ></v-text-field>
              <v-text-field filled readonly label="IMC" :value="imc"></v-text-field>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      height: 0,
      weight: 0,
    };
  },
  computed: {
    imc: {
      get: function() {
        if (this.height == 0 || this.weight == 0) return 0;
        let imc = this.weight / (this.height * this.height);
        imc = Math.round(imc * 10) / 10;
        return imc;
      },
    },
  },
};
</script>

<template>
  <div id="calcIMC">
    <div class="row">
      <img
        src="../assets/logo.png"
        width="50px"
      >
        <h2>
          {{ title }}
        </h2>
    </div>

    <form class="mainContent">
      <label>
        Altura:
        <input autofocus type="number" min="0" step="0.01" v-model="height"> (m)
      </label>
      <label>
        Peso:
        <input autofocus type="number" min="0" v-model="weight"> (kg)
      </label>
      <label>
        IMC:
        <input autofocus type="number" :value="imc" disabled="disabled">
      </label>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
  },
  data() {
    return {
      height: 0,
      weight: 0,
    }
  },
  computed: {
    imc: {
      get: function () {
        let imc = this.weight / ( this.height * this.height );
        imc = Math.round(imc * 10) / 10;
        return imc
      }
    }
  }
}
</script>

<style scoped>
.row {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
}
.mainContent {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px;
}
input {
  margin-bottom: 10px;
}
</style>
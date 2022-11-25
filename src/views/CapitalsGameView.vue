<script>
import countries from "/src/datasets/countries.json";
import CountryComponent from "../components/CountryComponent.vue";

export default {
  name: "CapitalsGameView",
  components: {
    CountryComponent,
  },
  data() {
    return {
      country: {},
      capital: "",
      puntaje: 0,
    };
  },
  created() {
    this.country = countries[Math.floor(Math.random() * countries.length)];
  },
  methods: {
    setCapital(e) {
      //TODO: implementar. fija la capital del input.
    },
    adivinarCapital() {
      //TODO: implementar. verifica se la adivinanza es correcta.
      if(capital == this.country.capital){
        puntaje++
      }
     
      this.$router.push({name: 'CapitalsGameView'}) 
    },
  },
};
</script>

<template>
  <h1>Puntaje: {{ puntaje }}</h1>
  <div class="countries">
    <!-- TODO: usar los metodos definidos arriba dentro del input para llenar el estado de la capital a adivinar-->
    <input
      placeholder="Adivina la capital"
    />
    <button @click="adivinarCapital">Adivina!</button>
    <div class="countries-container">
      <!--TODO: CREAR EL COMPONENTE PARA VISUALIZAR EL PAIS-->
     <div countries="city">
    <h1> Pais {{ country_name  || 'No props passed yet' }}</h1>
    <p> Estado{{ state_name  || 'No props passed yet' }}</p>
    <p> Latitud {{ latitude || 'No props passed yet' }}</p>
    <p> Longitud {{ longitude  || 'No props passed yet' }}</p>
    <img
      width="200"
      height="200"
      v-bind:src=' "https://countryflagsapi.com/png/"+ country.code '
    />
  </div>
  </div>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  .countries {
    align-items: center;
  }

  input {
    line-height: 2em;
  }

  .countries-container {
    margin-left: 35%;
    align-items: center;
    overflow-y: auto;
    vertical-align: middle;
    padding: 10px;
  }
}
</style>

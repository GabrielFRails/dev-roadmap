<template>
  <v-app>
    <tittle-padrao></tittle-padrao>
    <tabela-pesquisa></tabela-pesquisa>
  </v-app>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "font-awesome/css/font-awesome.css";
import TittlePadrao from "./components/TittlePadrao.vue";
import TabelaPesquisa from "./components/TabelaPesquisa.vue";

export default {
  name: "app",
  components: {
    TittlePadrao,
    TabelaPesquisa,
  },
  data: function () {
    return {
      prefix: "",
      sufix: "",
      prefixes: ["Air", "Jet", "Flight"],
      sufixes: ["Hub", "Station", "Mart"],
      domains: [
        "AirHub",
        "AirStation",
        "AirMart",
        "JetHub",
        "JetStation",
        "JetMart",
        "FlightHub",
        "FlighStation",
        "FlightMart",
      ],
    };
  },
  methods: {},
};
</script>

<style>
</style>
<template>
  <v-container>
    <div>
      <v-card>
        <v-card-title>
          <v-select :items="statusList" label="Filtros" v-model="selectedFilterItem"></v-select>
          <!-- <v-text-field
            v-model="search"
            append-icon="mdi-magnify"
            label="Search"
            single-line
            hide-details
          ></v-text-field> -->
        </v-card-title>
        <v-data-table :headers="headers" :items="computedItems"></v-data-table>
      </v-card>
    </div>
  </v-container>
</template>

<script>
export default {
  name: "TabelaPesquisa",
  data: function () {
    return {
      statusList: ["DEAL", "REJECTED", "TIMEOUT"],
      selectedFilterItem: "",
      headers: [
        { text: "status", value: "status" },
        {
          text: "BRL",
          align: "start",
          value: "Amount_BRL",
        },
        { text: "CCY", value: "Amount_CCY" },
        { text: "USD", value: "Amount_USD" },
        { text: "CNPJ", value: "Client_CNPJ" },
        { text: "Cliente", value: "Client_Name" },
        { text: "BACEN", value: "CurrencyCode_BACEN" },
        { text: "ISO Code", value: "CurrencyCode_ISO" },
        { text: "Client Rate", value: "FX_ClientRate" },
        { text: "Tipo de Mercado", value: "MarketType" },
        { text: "Produto", value: "Product" },
        { text: "Taxa de Custo", value: "SPOT_CCY_CostRate" },
        { text: "Id da Transação", value: "Transaction_ID" },
        { text: "Tipo da Transação", value: "Transaction_Type" },
      ],
      appData: [
        {
          status: "DEAL",
          Amount_BRL: 56035.11,
          Amount_CCY: 10000.02,
          Amount_USD: 56010.11,
          Client_CNPJ: "00001180000126",
          Client_Name: "Eletrobras - CENTRAIS ELETRICAS BRASILEIRAS SA",
          CurrencyCode_BACEN: 220,
          CurrencyCode_ISO: "USD",
          FX_ClientRate: 5.6035,
          MarketType: "1",
          Product: "FXSPOT",
          SPOT_CCY_CostRate: 5.6015,
          Trading_Day: "2021-11-08",
          Transaction_ID: "52420644",
          Transaction_Type: "IMPORTACAO_EXPORTACAO",
        },
        {
          status: "REJECTED",
          Amount_BRL: 56035.11,
          Amount_CCY: 10000.02,
          Amount_USD: 56010.11,
          Client_CNPJ: "00001180000126",
          Client_Name: "Eletrobras - CENTRAIS ELETRICAS BRASILEIRAS SA",
          CurrencyCode_BACEN: 220,
          CurrencyCode_ISO: "USD",
          FX_ClientRate: 5.6035,
          MarketType: "1",
          Product: "FXSPOT",
          SPOT_CCY_CostRate: 5.6015,
          Trading_Day: "2021-11-08",
          Transaction_ID: "52420644",
          Transaction_Type: "IMPORTACAO_EXPORTACAO",
        },
        {
          status: "TIMEOUT",
          Amount_BRL: 56035.11,
          Amount_CCY: 10000.02,
          Amount_USD: 56010.11,
          Client_CNPJ: "00001180000126",
          Client_Name: "Eletrobras - CENTRAIS ELETRICAS BRASILEIRAS SA",
          CurrencyCode_BACEN: 220,
          CurrencyCode_ISO: "USD",
          FX_ClientRate: 5.6035,
          MarketType: "1",
          Product: "FXSPOT",
          SPOT_CCY_CostRate: 5.6015,
          Trading_Day: "2021-11-08",
          Transaction_ID: "52420644",
          Transaction_Type: "IMPORTACAO_EXPORTACAO",
        },
        {
          status: "DEAL",
          Amount_BRL: 56035.11,
          Amount_CCY: 10000.02,
          Amount_USD: 56010.11,
          Client_CNPJ: "00001180000126",
          Client_Name: "Eletrobras - CENTRAIS ELETRICAS BRASILEIRAS SA",
          CurrencyCode_BACEN: 220,
          CurrencyCode_ISO: "USD",
          FX_ClientRate: 5.6035,
          MarketType: "1",
          Product: "FXSPOT",
          SPOT_CCY_CostRate: 5.6015,
          Trading_Day: "2021-11-08",
          Transaction_ID: "52420644",
          Transaction_Type: "IMPORTACAO_EXPORTACAO",
        },
      ],
    };
  },
  computed: {
      computedItems() {
          const filteredItems = this.appData.filter(item => item.status === this.selectedFilterItem);
          return filteredItems;
      }
  }
};
</script>

<style>
</style>
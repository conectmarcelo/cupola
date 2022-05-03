<template>
  <v-container>
    <v-row>
      <v-col cols="12" class="teste">
        <div class="prototype">
          <div class="conectOverviweCard" v-for="(dado, i) in dados" :key="i">
            <div v-if="i==active" class="conectaTooltip">
              <p class="hint">{{dado.legenda}}</p>
              <div class="arrow"></div>
            </div>
            <div class="conectaIcon">
              <v-icon
                class="info"
                @mouseover="mouseOver(i)"
                @mouseleave="mouseLeave()"
              >mdi-information-outline</v-icon>
            </div>
            <div class="card">
              <v-row class="wrap">
                <div class="symbol">
                  <v-avatar class="circle" :color="dado.cor" size="55.37" />
                  <v-icon id="icon" :color="dado.cor">{{dado.icone}}</v-icon>
                </div>
                <div class="content">
                  <P class="value">{{dado.valor}}</P>
                  <p class="label">{{ dado.nome }}</p>
                </div>
              </v-row>
            </div>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Dashboard",

  data() {
    return {
      active: null,

      dados: [
        {
          nome: "Coversões",
          valor: "2.5 M",
          icone: "mdi-email",
          cor: "blue",
          legenda: "Conversão é a ação do envio de qualquer formulário.",
        },
        {
          nome: "Leads",
          valor: "965.321",
          icone: "mdi-account",
          cor: "purple",
          legenda:
            "Lead é um contato individual do cliente ao enviar formulários.",
        },
        {
          nome: "Cust por lead",
          valor: "R$ 10",
          icone: "mdi-currency-usd",
          cor: "green",
          legenda:
            "É o cálculo do investimento utilizado pela quantidade de leads gerados no período.",
        },
      ],
    };
  },

  methods: {
    mouseOver: function (i) {
      this.active = i;
    },
    mouseLeave: function () {
      this.active = null;
    },
  },
};
</script>

<style src="./style.scss" lang='scss' scoped/>

<script>
export default {
  data() {
    return {
      valor: 0,
      gorj: "",
      pessoas: 1,
    };
  },
  methods: {
    calcular() {
      const valor = this.valor;
      const gorj = this.gorj;
      const pessoas = this.pessoas;
      let gorjeta = 0;
      let total = {};
      gorjeta = valor * (gorj / 100);
      total = (valor + gorjeta) / pessoas;
      total = Math.round(total * 100) / 100;
      total = total.toFixed(2);
      console.log(total);
      document.getElementById("resultado").innerHTML = total;
    },
  },
};
</script>

<template>
  <div class="main">
    <h1><strong>Ifoode</strong></h1>

    <form>
      <label>
        <p>Valor do pedido</p>
        <input type="number" v-model="valor" id="valor" />
      </label>

      <label>
        <p>Gorjeta e qualidade de entrga</p>
        <select v-model="gorj" id="gorjeta">
          <option value="5">serviço péssimo - 5%</option>
          <option value="10">serviço ruim - 10%</option>
          <option value="15">serviço OK - 15%</option>
          <option value="20">serviço bom - 20%</option>
          <option value="25">serviço mais que bom - 25%</option>
          <option value="30">serviço excepcional - 30%</option>
        </select>
      </label>

      <label>
        <p>Quantas pessoas vão dividir a Conta?</p>
        <input v-model="pessoas" type="number" id="pessoas" />
      </label>

      <label>
        <button type="button" @click="calcular">CALCULAR</button>
      </label>
      <label>
        <p>Valor</p>
        <span id="resultado">R$</span>
      </label>
    </form>
  </div>
</template>
<style>
@import "@/assets/style.css";
</style>

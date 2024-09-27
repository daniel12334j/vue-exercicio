<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
      resultado: 0,
    };
  },
  methods: {
    calcular() {
      const num1 = parseFloat(this.numero1);
      const num2 = parseFloat(this.numero2);

      switch (this.operacao) {
        case '+':
          this.resultado = num1 + num2;
          break;
        case '-':
          this.resultado = num1 - num2;
          break;
        case '*':
          this.resultado = num1 * num2;
          break;
        case '/':
          this.resultado = num2 !== 0 ? num1 / num2 : 'Erro: Divisão por zero';
          break;
      }
    },
  },
};
</script>

<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input type="number" v-model="numero1" @input="calcular" placeholder="Número 1" />
      <input type="number" v-model="numero2" @input="calcular" placeholder="Número 2" />
      
      <select v-model="operacao" @change="calcular">
        <option value="+">Adicionar</option>
        <option value="-">Subtrair</option>
        <option value="*">Multiplicar</option>
        <option value="/">Dividir</option>
      </select>
    </div>

    <h2>Resultado: {{ resultado }}</h2>
  </div>
</template>



<style>
/* Estilos opcionais */
#app {
  max-width: 300px;
  margin: auto;
  text-align: center;
}
input, select {
  margin: 10px 0;
  width: 100%;
}
</style>

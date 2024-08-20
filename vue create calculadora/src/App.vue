<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="calculator">
      <input type="number" v-model.number="number1" placeholder="Digite o primeiro número">
      <select v-model="operation">
        <option value="add">Somar</option>
        <option value="subtract">Subtrair</option>
        <option value="multiply">Multiplicar</option>
        <option value="divide">Dividir</option>
      </select>
      <input type="number" v-model.number="number2" placeholder="Digite o segundo número">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add'
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.number1 + this.number2;
        case 'subtract':
          return this.number1 - this.number2;
        case 'multiply':
          return this.number1 * this.number2;
        case 'divide':
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    }
  }
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}

.calculator {
  display: inline-block;
  padding: 20px;
  border: 2px solid #ddd;
  border-radius: 8px;
  box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.1);
}

input, select {
  margin: 5px;
  padding: 8px;
  font-size: 16px;
}
</style>

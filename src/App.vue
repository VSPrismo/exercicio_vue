<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>

    <div class="input-group">
      <input v-model="number1" type="number" placeholder="Número 1">
      <select v-model="operator">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input v-model="number2" type="number" placeholder="Número 2">
    </div>

    <h2>Resultado: {{ resultado }}</h2>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      number1: 0,
      number2: 0,
      operator: '+',
    };
  },
  computed: {
  resultado() {
    const num1 = parseFloat(this.number1);
    const num2 = parseFloat(this.number2);

    switch (this.operator) {
      case '+':
        return num1 + num2;
      case '-':
        return num1 - num2;
      case '*':
        return num1 * num2;
      case '/':
        return num1 / num2;
      default:
        return 0;
    }
  },
},

};
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  margin-top: 20px;
}

.input-group {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}

.input-group input {
  width: 100px;
  margin: 0 10px;
}

h1, h2 {
  margin: 0;
}
</style>

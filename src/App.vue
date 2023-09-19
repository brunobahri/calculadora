<template>
  <div class="calculator">
    <input v-model="num1" @input="calculate" type="number" placeholder="Número 1" />
    <select v-model="operator" @change="calculate">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input v-model="num2" @input="calculate" type="number" placeholder="Número 2" />
    <div class="result">
      Resultado: {{ result }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case '+':
          this.result = this.num1 + this.num2;
          break;
        case '-':
          this.result = this.num1 - this.num2;
          break;
        case '*':
          this.result = this.num1 * this.num2;
          break;
        case '/':
          this.result = this.num1 / this.num2;
          break;
        default:
          this.result = 0;
      }
    },
  },
};
</script>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
}

input,
select {
  margin: 10px;
  padding: 5px;
  font-size: 16px;
}

.result {
  font-size: 20px;
  font-weight: bold;
}
</style>

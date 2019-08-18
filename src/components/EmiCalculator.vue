<template>
  <div >Principal
  <input v-model="principal" @change="calculateEMI" placeholder="Principal Amount">
  <br>Rate of Interest %
  <input v-model="interest" @change="calculateEMI" placeholder="Interest %">
  <br>Loan Tenure
  <input v-model="tenure" @change="calculateEMI" placeholder="Period">
  <br>
    <p>EMI Amount is: {{ emi }}</p>
    <p>Interest payable is: {{ interestAmount }}</p>
    <p>Total Amount is: {{ totalAmount }}</p>
  </div>
</template>
<script>
export default {
  name: 'EmiCalculator',
  data() {
    return {
      principal: 100000,
      interest: 12,
      tenure: 12,
      emi: 0,
      interestAmount: 0,
      totalAmount: 0,
    };
  },
  methods: {
    calculateEMI() {
      console.log('Calculating EMI');
      const r = (this.interest / 12) / 100;
      const emi = this.principal * r * (((1 + r) ** this.tenure) / (((1 + r) ** this.tenure) - 1));
      this.emi = emi.toFixed(2);
      this.totalAmount = (this.emi * this.tenure).toFixed(2);
      this.interestAmount = (this.totalAmount - this.principal).toFixed(2);
    },
  },
  computed: {

  },
  mounted() {
    this.calculateEMI();
  },
};
</script>

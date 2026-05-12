<template>
  <div>
    <v-card width="500">
      <v-card-text>
      <v-text-field v-model="firstNumber" label="Enter 1st Number"></v-text-field>

      <v-text-field v-model="secondNumber" label="Enter 2nd Number"></v-text-field>
      
      <v-text-field v-model="total" label="Total:"></v-text-field>

      <v-btn color="primary" @click="calculate" block>CALCULATE</v-btn>
      </v-card-text>
    </v-card>
  </div>
</template>

<script setup>
const firstNumber = ref(0);
const secondNumber = ref(0);
const total = ref(0);

function calculate() {
  if (total.value = Number(firstNumber.value) + Number(secondNumber.value) ) {
   //total = firstNumber + secondNumber
  } else {
    alert("cannot be read")
  }
}
</script>

<style>

</style>
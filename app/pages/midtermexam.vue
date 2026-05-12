<template>
  <div>

      <v-icon size="35" color="black">mdi-calculator</v-icon>
      <v-text>Calculator</v-text>


    <v-card width="500" class="pa-4">
      
 
      <v-radio-group v-model="operation" inline>
        <v-radio label="Addition" 
        value="Addition">
      </v-radio>

        <v-radio label="Subtract" 
        value="Subtraction">
      </v-radio>

        <v-radio label="Multiplication" 
        value="Multiplication">
      </v-radio>
        <v-radio label="Division"
        value="Division">
      </v-radio>


      </v-radio-group>



      <v-form>
        <v-text-field v-model="firstNumber" label="Enter 1st Number" ></v-text-field>

        <v-text-field v-model="secondNumber" label="Enter 2nd Number" ></v-text-field>

        <v-text-field v-model="total" label="Total"></v-text-field>

        <v-btn color="primary" @click="calculate" block>
          Calculate
        </v-btn>
      </v-form>

    </v-card>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const firstNumber = ref(0)
const secondNumber = ref(0)
const total = ref(0)
const operation = ref('add')


function calculate() {
  const num1 = Number(firstNumber.value)
  const num2 = Number(secondNumber.value)


  if (operation.value == 'Addition') {
    total.value = num1 + num2

  } else if (operation.value == 'Subtraction') {
    total.value = num1 - num2

  } else if (operation.value == 'Multiplication') {
    total.value = num1 * num2

  } else if (operation.value == 'Division') {
    if (num2 === 0) {
      alert("Cannot divide by zero")
      return
    }
    total.value = num1 / num2

  } else {
    alert("Invalid operation")
  }
}
</script>

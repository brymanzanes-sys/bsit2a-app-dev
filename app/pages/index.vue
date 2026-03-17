<template>
  <div class="d-flex justify-center align-center" 
  style="height: 100vh"> 

    <v-card width="400" class="text-center" elevation="12">
      <!-- LOGO -->
       <v-icon size="80" color="black" class="pt-10">mdi-instagram</v-icon>
      <v-card-text class="py-10">
        <!-- USERNAME TEXTFIELD-->
         <v-text-field 
         variant="outlined"
         v-model="username" 
         label="Username" 
         prepend-inner-icon="mdi-account" 
         clearable
         >

        </v-text-field>


        <!-- PASSWORD TEXTFIELD-->

        <v-text-field 
         variant="outlined"
         v-model="password"
         flat 
         label="Password" 
         prepend-inner-icon="mdi-lock"
         type="password" 
         clearable
         >

        </v-text-field>

        <!-- SIGN-IN BUTTON-->

        <v-btn color="#EEEEEE" @click="login()"
        block>SIGN IN</v-btn>
        
      </v-card-text>
    </v-card>


  </div>
</template>

<script setup>
definePageMeta({
  layout: 'auth',
});
const defaultUsername = ref("admin");
const defaultPassword = ref("admin123");
const username = ref("");
const password = ref("");

function login() {
  alert("LOGIN FUNCTION CALLED");
}


</script>
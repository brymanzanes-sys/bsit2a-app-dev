<template>
  <v-app>
    
    <v-navigation-drawer 
    v-model="drawer" :rail="rail"
        permanent
        @click="rail = false"
        
      >
        <template v-slot:prepend>
          <v-list-item
            lines="two"
            prepend-avatar="https://randomuser.me/api/portraits/women/81.jpg"
            subtitle="Logged in yarn"
            title="Daniluh"
          ></v-list-item>
        </template>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-home-city" title="Dashboard" value="dashboard" to="/dashboard"></v-list-item>
          <v-list-item prepend-icon="mdi-account-group-outline" title="Remedial" value="remedial"
          to="/remedial"
          ></v-list-item>
          <v-list-item prepend-icon="mdi-calculator" title="Calculate" value="Calculate" to="/calculate"></v-list-item>
          <v-list-item prepend-icon="mdi-calculator" title="MidtermExam" value="midtermexam" to="/midtermexam"></v-list-item>
          <v-list-item prepend-icon="mdi-clock" title="To do" value="Todo" to="/Todo"></v-list-item>
        </v-list>
      </v-navigation-drawer>

    <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon  @click.stop="rail = !rail"></v-app-bar-nav-icon>
  </template>

  <v-app-bar-title>Application Bar</v-app-bar-title>
</v-app-bar>

<v-main>   
  <v-container fluid>
    <slot />
  </v-container>
</v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
const drawer = ref(true)
const rail = ref(true)
</script>

<style>

</style>
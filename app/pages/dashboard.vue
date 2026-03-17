<template>
  <div>
    <v-row>
      <v-col cols="12" md="3">
        <v-card height="120" color="blue">
          <v-card-text>
            <v-row align="center"><!-- left column -->
              <v-col>
                <v-icon size="80">mdi-account</v-icon>
              </v-col>

              <v-col>
                <v-row no no-gutters>
                  <!-- right column -->
                  <v-col cols="12" class="text-right text-h5 text-uppercase" >
                    Student
                  </v-col>

                  <v-col cols="12" class="text-right text-h3 font-weight-bold">
                    120
                  </v-col>

                </v-row>
              </v-col>

            </v-row>
          </v-card-text>
        </v-card>        
      </v-col>

      <v-col cols="12" md="3">
        <v-card height="120" color="red">
          <v-card-text>
            <v-row align="center"><!-- left column -->
              <v-col>
                <v-icon size="80">mdi-home</v-icon>
              </v-col>

              <v-col>
                <v-row no no-gutters>
                  <!-- right column -->
                  <v-col cols="12" class="text-right text-h5 text-uppercase" >
                    Account
                  </v-col>

                  <v-col cols="12" class="text-right text-h3 font-weight-bold">
                    64
                  </v-col>

                </v-row>
              </v-col>

            </v-row>
          </v-card-text>
        </v-card>
      </v-col>

      <v-col cols="12" md="3">
        <v-card height="120" color="green">
          <v-card-text>
            <v-row align="center"><!-- left column -->
              <v-col>
                <v-icon size="80">mdi-message</v-icon>
              </v-col>

              <v-col>
                <v-row no no-gutters>
                  <!-- right column -->
                  <v-col cols="12" class="text-right text-h5 text-uppercase" >
                    Pautang
                  </v-col>

                  <v-col cols="12" class="text-right text-h3 font-weight-bold">
                    90
                  </v-col>

                </v-row>
              </v-col>

            </v-row>
          </v-card-text>
        </v-card>
      </v-col>

      <v-col cols="12" md="3">
        <v-card height="120" color="purple">
          <v-card-text>
            <v-row align="center"><!-- left column -->
              <v-col>
                <v-icon size="80">mdi-phone</v-icon>
              </v-col>

              <v-col>
                <v-row no no-gutters>
                  <!-- right column -->
                  <v-col cols="12" class="text-right text-h5 text-uppercase" >
                    Contact
                  </v-col>

                  <v-col cols="12" class="text-right text-h3">
                    12
                  </v-col>

                </v-row>
              </v-col>

            </v-row>
          </v-card-text>
        </v-card>
      </v-col>



   <v-col cols="8" md="8">
    <v-card height="460" color="#EEEEEE">
    <v-data-table
    ::headers="headers"
    :items="plants"
    density="compact"
    item-key="name"
  ></v-data-table>
    </v-card>
   </v-col>

   <v-row>
    <v-col>
    <v-col cols="3" md="12">
    <v-card color="#385F73">
                <v-card-title class="text-h5">
                  Unlimited music now
                </v-card-title>

                <v-card-subtitle>
                  Listen to your favorite artists and albums whenever and wherever, online and offline.
                </v-card-subtitle>

                <v-card-actions>
                  <v-btn text="Listen Now" variant="text"></v-btn>
                </v-card-actions>
              </v-card>

   </v-col>
   <v-col cols="3" md="12">
    <v-card color="#1F7087">
                <div class="d-flex flex-no-wrap justify-space-between">
                  <div>
                    <v-card-title class="text-h5">
                      Supermodel
                    </v-card-title>

                    <v-card-subtitle>Foster the People</v-card-subtitle>

                    <v-card-actions>
                      <v-btn
                        class="ms-2"
                        size="small"
                        text="START RADIO"
                        variant="outlined"
                      ></v-btn>
                    </v-card-actions>
                  </div>

                  <v-avatar
                    class="ma-3"
                    rounded="0"
                    size="125"
                  >
                    <v-img src="https://cdn.vuetifyjs.com/images/cards/foster.jpg"></v-img>
                  </v-avatar>
                </div>

    </v-card>
   </v-col>

      <v-col cols="3" md="12">
    <v-card color="#952175">
                <div class="d-flex flex-no-wrap justify-space-between">
                  <div>
                    <v-card-title class="text-h5">
                      Halcyon Days
                    </v-card-title>

                    <v-card-subtitle>Ellie Goulding</v-card-subtitle>

                    <v-card-actions>
                      <v-btn
                        class="ms-2"
                        icon="mdi-play"
                        variant="text"
                      ></v-btn>
                    </v-card-actions>
                  </div>

                  <v-avatar
                    class="ma-3"
                    rounded="0"
                    size="125"
                  >
                    <v-img src="https://cdn.vuetifyjs.com/images/cards/halcyon.png"></v-img>
                  </v-avatar>
                </div>
              </v-card>
   </v-col>

   </v-col>
   </v-row>
</v-row>

   <!--<v-fab
   :absolute="false"
   :app="true"
   color="primary"
   location="right bottom"
   size="large"
   icon
   @click="dialog = !dialog" 
   >
   <v-icon>mdi-plus</v-icon>
  </v-fab> -->

  <!-- <v-dialog v-model="dialog" width="500">
    <v-card>
      
      <v-toolbar>
        <v-toolbar-title>
          Create New Item
        </v-toolbar-title>
      </v-toolbar>
      <v-card-text> </v-card-text>

    </v-card>
  </v-dialog> -->



  </div>
</template>

<script lang="ts" setup>
  const headers = [
    { title: 'Plant', align: 'start', sortable: false, key: 'name' },
    { title: 'Light', align: 'end', key: 'light' },
    { title: 'Height', align: 'end', key: 'height' },
    { title: 'Pet Friendly', align: 'end', key: 'petFriendly' },
    { title: 'Price ($)', align: 'end', key: 'price' },
  ]

  const plants = [
    {
      name: 'Fern',
      light: 'Low',
      height: '20cm',
      petFriendly: 'Yes',
      price: 20,
    },
    {
      name: 'Snake Plant',
      light: 'Low',
      height: '50cm',
      petFriendly: 'No',
      price: 35,
    },
    {
      name: 'Monstera',
      light: 'Medium',
      height: '60cm',
      petFriendly: 'No',
      price: 50,
    },
    {
      name: 'Pothos',
      light: 'Low to medium',
      height: '40cm',
      petFriendly: 'Yes',
      price: 25,
    },
    {
      name: 'ZZ Plant',
      light: 'Low to medium',
      height: '90cm',
      petFriendly: 'Yes',
      price: 30,
    },
    {
      name: 'Spider Plant',
      light: 'Bright, indirect',
      height: '30cm',
      petFriendly: 'Yes',
      price: 15,
    },
    {
      name: 'Air Plant',
      light: 'Bright, indirect',
      height: '15cm',
      petFriendly: 'Yes',
      price: 10,
    },
    {
      name: 'Peperomia',
      light: 'Bright, indirect',
      height: '25cm',
      petFriendly: 'Yes',
      price: 20,
    },
    {
      name: 'Aloe Vera',
      light: 'Bright, direct',
      height: '30cm',
      petFriendly: 'Yes',
      price: 15,
    },
    {
      name: 'Jade Plant',
      light: 'Bright, direct',
      height: '40cm',
      petFriendly: 'Yes',
      price: 25,
    },
  ]
</script>

<style>

</style>

<template>
  <div class="Home">
    <v-container>
      <v-layout>
        <v-row justify="center">
          <v-col cols="42" lg="8" justify="center">
            <v-row :align="align" no-gutters style="height: 150px">
              <v-col v-for="n in 30" :key="n">
                <v-container>
                 <CartaLibro/>
                </v-container>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-layout>
    </v-container>
  </div>
</template>

{<script>
import Cartalibro from './component/Cartalibro'
export default {
  component : {
    Cartalibro,
  },
  data() {
      return {
          CartaLibro: {
       id: 1, title: 'el salta montes', author: 'juan pedro', price: '325' 
       }
    
      }
  
}
}
</script>


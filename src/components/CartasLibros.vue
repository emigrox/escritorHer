<template>
  <div class="Cartas Libros">
    <v-container>
      <v-layout>
        <v-row justify="center">
          <v-col cols="42" lg="8" justify="center">
            <v-row :align="align" no-gutters style="height: 150px">
              <v-col v-for="n in 30" :key="n">
               <v-card>queso</v-card>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-layout>
    </v-container>
  </div>
</template>


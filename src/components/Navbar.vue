<template>
  <v-app-bar color="deep-purple accent-4" dense elevate-on-scroll dark app>
    <v-app-bar-nav-icon></v-app-bar-nav-icon>

    <v-toolbar-title>Escritor app</v-toolbar-title>

    <v-spacer></v-spacer>

    <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon to="/PdfReader"
          v-bind="attrs"
            v-on="on">
      <v-icon>mdi-file-document-multiple</v-icon>
    </v-btn>
        </template>
        <span
            v-bind="attrs"
            v-on="on"
          >Pdf Reader</span>
      </v-tooltip>

    <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon to="/"
          v-bind="attrs"
            v-on="on">
      <v-icon>mdi-home</v-icon>
    </v-btn>
        </template>
        <span
            v-bind="attrs"
            v-on="on"
          >Home</span>
      </v-tooltip>
    
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon to="/Signup"
          v-bind="attrs"
            v-on="on">
      <v-icon>mdi-account-box</v-icon>
    </v-btn>
        </template>
        <span
            v-bind="attrs"
            v-on="on"
          >Signup</span>
      </v-tooltip>

       <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon to="/Login"
          v-bind="attrs"
            v-on="on">
      <v-icon>mdi-account</v-icon>
    </v-btn>
        </template>
        <span
            v-bind="attrs"
            v-on="on"
          >Login</span>
      </v-tooltip>


    
    <v-menu left bottom>
      
      <template v-slot:activator="{ on, attrs }">
        <v-btn icon v-bind="attrs" v-on="on">
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </template>
     <span
       v-bind="attrs"
            v-on="on"
          >Menu</span>
      <v-list>
        <v-list-item v-for="n in 5" :key="n" @click="() => {}">
          <v-list-item-title>Option {{ n }}</v-list-item-title>
        </v-list-item>
      </v-list>
       
         
   </v-menu>
    
  </v-app-bar>
</template>

<script>
export default {
  data: () => ({ value: 1 }),
};
</script>

<style>
</style>
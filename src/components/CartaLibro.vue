 <template>
  <v-container>
    <v-card outlined tile>
      <v-btn>
        <v-icon>mdi-cards-spade</v-icon>
      </v-btn>
      <v-input v-bind="id"> </v-input>
      <v-input v-bind="title"> </v-input>
      <v-input v-bind="author"> </v-input>
      <v-input v-bind="price"> </v-input>
    </v-card>
  </v-container>
</template>
<template>
  <v-app>
    <v-container>
        <v-layout justify-space-around>
      <v-card>
        <v-container>
          <v-card-title> Login</v-card-title>
          <v-form ref="form" lazy-validation v-model="valid">
            <v-text-field
              v-model="email"
              :rules="rulesEmail"
              label="Email"
              type="email"
              prepend-icon="mdi-mail"
              required
            ></v-text-field>

            <v-text-field
              v-model="password"
              label="Password"
              :rules="rulepass"
              prepend-icon="mdi-lock"
              type="password"
              required
            ></v-text-field>
            <v-btn @click="validateLogin" :disabled="!valid" align-center
              >Login</v-btn
            >
          </v-form>
        </v-container>
      </v-card>
        </v-layout>
    </v-container>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    email: "",
    password: "",
    valid: true,
    rulepass: [(v) => !!v || "Password is required"],
  }),
  computed: {
    rulesEmail() {
      const rules = [];
      const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      const rule1 = (v) => pattern.test(v) || `Email not allowed`;
      rules.push(rule1);
      return rules;
    },
  },
  methods: {
    validateLogin() {
      this.$refs.form.validate();
    },
  },
};
</script>

<style>
</style>
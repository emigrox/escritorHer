<template>
  <v-app>
    <v-container>
      <v-layout>
        <v-row justify="center">
          <v-col cols="12" md="4" justify="center">
            <v-card>
              <v-container>
                <v-form ref="form" lazy-validation>
                  <h2 class="text-center">Login</h2>
                  <v-text-field
                    v-model="email"
                    :rules="rulesEmail"
                    label="Email"
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="password"
                    label="Password"
                    :rules="rulesPassword"
                    required
                  ></v-text-field>

                  <div></div>
                  <div></div>

                  <v-container>
                    <v-btn block @click="validateLogin">Login</v-btn>
                  </v-container>
                </v-form>
              </v-container>
            </v-card>
          </v-col>
        </v-row>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    email: "",
    password: "",
    rulepass: [(v) => !!v || "Password is required"],
  }),
  computed: {
    rulesPassword() {
      const rules = [];

      const ruleLowerCase = (v) =>
        /[a-z]/.test(v) || `Password must contain a lower case letter`;
      rules.push(ruleLowerCase);

      const ruleUpperCase = (v) =>
        /[A-Z]/.test(v) || `Password must contain a Upper Caser letter.`;
      rules.push(ruleUpperCase);

      const ruleDigit = (v) =>
        /[0-9]/.test(v) || `Password must contain number.`;
      rules.push(ruleDigit);

      const ruleSpecialChar = (v) =>
        /[!@#$%^&*]/.test(v) ||
        `Pasword must contain a special char(!@#$%^&*).`;
      rules.push(ruleSpecialChar);

      const rule2 = (v) =>
        (v || "").length >= 8 || `A minimum of 8 characters is needed.`;
      rules.push(rule2);

      return rules;
    },
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
      if (this.$refs.form.validate()) {
        this.$router.push("UserAcount");
      }
    },
  },
};
</script>

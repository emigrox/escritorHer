<template>
  <v-app>
      <v-container>
          <v-row justify="center">
              <v-col cols="12" md="4">
                  <h2 class="text-center">Login</h2>
              </v-col>
          </v-row> 
          <v-row justify="center">
              <v-col cols="12" md="4">
                  <v-form ref="form"
                  lazy-validation 
                  v-model="valid"
                  >
                    <v-text-field
                    v-model="email"
                    :rules="rulesEmail"
                    label="Email"
                    required
                    ></v-text-field>
                    <v-text-field
                    v-model="password"
                    label="Password"
                    :rules="rulepass"
                    required 
                    ></v-text-field>
                    <v-btn @click="validateLogin"
                    :disabled="!valid"
                    >Login</v-btn>
                </v-form>
              </v-col>
          </v-row>
      </v-container>
  </v-app>
</template>

<script>
export default {
    data: () => ({
        email: '',
        password: '',
        valid: true,
        rulepass: [v => !!v || 'Password is required']       
    }),
    computed: {
         rulesEmail() {
            const rules = []
            const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
            const rule1 = 
                v => pattern.test(v) || `Email not allowed`
            rules.push(rule1)
            return rules
            },
    },
    methods: {
        validateLogin(){
            this.$refs.form.validate()
        }
    },

};
</script>

<style>
</style>
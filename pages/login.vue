<template>
  <v-app id="inspire">
    <v-content>
      <v-container fluid fill-height>
        <v-layout align-center justify-center>
          <v-flex xs12 sm8 md6>
            <v-card class="elevation-12">
              <v-toolbar dark color="primary">
                <v-toolbar-title>Авторизация</v-toolbar-title>
              </v-toolbar>
              <v-card-text>
                <v-form>
                  <v-text-field
                    v-model="email"
                    prepend-icon="person"
                    name="login"
                    label="Логин"
                    type="text"
                  ></v-text-field>
                  <v-text-field
                    id="password"
                    v-model="password"
                    prepend-icon="lock"
                    name="password"
                    label="Пароль"
                    type="password"
                  ></v-text-field>
                </v-form>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="primary" @click="login">Войти</v-btn>
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    email: '',
    password: ''
  }),
  methods: {
    login() {
      // this.$auth.loginWith('local', {
      //   data: {
      //     username: this.email,
      //     password: this.password
      //   }
      // })
      this.$auth.loginWith('github')
    }
  }
}
</script>

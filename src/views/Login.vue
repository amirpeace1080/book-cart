<template>
  <div id="app">
    <v-app>
      <v-card width="400" class="mx-auto my-auto">
        <v-card-title>
          <h1>Login</h1>
          <v-card-text>
            <v-form>
              <v-text-field label="Username *" prepend-icon="mdi-account-circle">
              </v-text-field>
              <v-text-field
                @click:append="showPassword = !showPassword"
                :type="showPassword ? 'text' : 'password'"
                label="Password *"
                prepend-icon="mdi-lock"
                :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              >
              </v-text-field>
            </v-form>
          </v-card-text>
        </v-card-title>
        <v-divider></v-divider>
        <v-card-actions class="ma-3">
          <v-btn to="/register" color="primary">Register</v-btn>
          <v-spacer></v-spacer>
          <v-btn color="secondary">Login</v-btn>
        </v-card-actions>
      </v-card>
    </v-app>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      showPassword: false,
    };
  },
};
</script>

<style>
</style>
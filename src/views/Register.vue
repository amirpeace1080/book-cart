<template>
  <div id="app">
    <v-app>
      <v-card width="400" class="mx-auto my-auto">
        <v-card-title>
          <h1>Register</h1>
          <v-card-text>
            <v-form>
              <v-text-field label="Firstname *"></v-text-field>
              <v-text-field label="Lastname *"></v-text-field>
              <v-text-field label="Username *"></v-text-field>
              <v-text-field
                @click:append="showPassword = !showPassword"
                :type="showPassword ? 'text' : 'password'"
                label="Password *"
                :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              >
              </v-text-field>
              <v-text-field
                @click:append="showPassword = !showPassword"
                :type="showPassword ? 'text' : 'password'"
                label="Confirm Password *"
                :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              >
              </v-text-field>

              <!-- <input v-validate="'required|email'" name="email" type="text">
              <span>{{ errors.first('email') }}</span> -->
            </v-form>
          </v-card-text>
        </v-card-title>
        <v-divider></v-divider>
        <v-card-actions class="ma-3">
          <v-spacer></v-spacer>
          <v-btn color="secondary">Register</v-btn>
        </v-card-actions>
      </v-card>
    </v-app>
  </div>
</template>

<script>
export default {
  name: "Register",
  data() {
    return {
      showPassword: false,
    };
  },
};
</script>

<style>
</style>
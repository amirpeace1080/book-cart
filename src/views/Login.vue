<template>
  <div id="app">
    <v-app>
      <v-card width="400" class="mx-auto my-auto">
        <v-card-title>
          <h1>Login</h1>
          <v-card-text>
            <v-form>
              <v-text-field
                v-model="username"
                label="Username *"
                prepend-icon="mdi-account-circle"
              >
              </v-text-field>
              <v-text-field
                v-model="password"
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
          <v-btn color="secondary" :disabled="isBtnDisabled" @click="login">Login</v-btn>
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
      username: '',
      password: '',
    };
  },
  methods: {
    login() {
      let username = this.username
      let password = this.password
      const user = username
      localStorage.setItem('username', user)

      this.$store.dispatch('login', {username, password}).then(() => {
        this.$fire({
            title: "Registration is done",
            // text: "برای ورود کد ملی و روز عبور خود را وارد نمایید",
            type: "success",
            confirmButtonText: "Ok",
          }).then((r) => {
            console.log(r.value);
          });
          this.$router.push('/')
          
      })
      .catch(() =>{
        this.$fire({
            title: "Error !",
            text: "The information entered is duplicate or incorrect",
            type: "error",
            confirmButtonText: "try again",
          }).then((r) => {
            console.log(r.value);
          });
      })
    }
  },
  computed: {
    isBtnDisabled() {
      return (
        this.username.length === 0 ||
        this.password.length === 0
      );
    },
  },
};
</script>

<style>
</style>
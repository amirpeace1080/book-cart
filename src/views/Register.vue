<template>
  <div id="app">
    <v-app>
      <v-card width="400" class="mx-auto my-auto">
        <v-card-title>
          <h1>Register</h1>
          <v-card-text>
            <v-form>
              <input
                v-model="form.firstName"
                class="inpute-all mt-5"
                placeholder="Firstname *"
              />

              <input
                v-model="form.lastName"
                class="inpute-all mt-4"
                placeholder="Lastname *"
              />
              <input
                v-model="form.userName"
                class="inpute-all mt-4"
                placeholder="Username *"
                v-validate="'min:5'"
                data-vv-as="field"
                name="min_field"
              />
              <span v-show="errors.has('min_field')" class="help red--text">{{
                errors.first("min_field")
              }}</span>

              <input
                v-model="form.password"
                class="inpute-all mt-4"
                placeholder="Password *"
                v-validate="'required'"
                name="password"
                :class="{ 'red--text': errors.has('password') }"
                ref="password"
              />

              <span v-show="errors.has('password')" class="help red--text">{{
                errors.first("password")
              }}</span>

              <input
                v-model="password_confirmation"
                class="inpute-all mt-4"
                placeholder="Confirm Password *"
                v-validate="'required|confirmed:password'"
                name="password_confirmation"
                :class="{ 'red--text': errors.has('password_confirmation') }"
                data-vv-as="password"
              />
              <span
                v-show="errors.has('password_confirmation')"
                class="help red--text"
                >{{ errors.first("password_confirmation") }}</span
              >

              <v-radio-group row required>
                <span class="mr-2">Gender: </span> {{ value }}
                <input
                  type="radio"
                  value="Male"
                  name="gender"
                  v-model="form.gender"
                />
                <label class="mr-3">Male</label>
                <input
                  type="radio"
                  value="Female"
                  name="gender"
                  v-model="form.gender"
                />
                <label>Female</label>
              </v-radio-group>
            </v-form>
          </v-card-text>
        </v-card-title>
        <v-divider></v-divider>
        <v-card-actions class="ma-3">
          <v-spacer></v-spacer>
          <v-btn color="secondary" :disabled="isBtnDisabled" @click="register"
            >Register</v-btn
          >
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
      form: {
        firstName: "",
        lastName: "",
        userName: "",
        password: "",
        gender: "",
      },
      password_confirmation: "",
    };
  },
  computed: {
    isBtnDisabled() {
      return (
        this.form.firstName.length === 0 ||
        this.form.lastName.length === 0 ||
        this.form.userName.length === 0 ||
        this.form.password.length === 0 ||
        this.password_confirmation.length === 0 ||
        this.form.gender.length === 0
      );
    },
  },
  methods: {
    register() {
      let form = this.form;
      this.$store
        .dispatch("register", form)
        .then(() => {
          this.$fire({
            title: "Registration is done",
            // text: "برای ورود کد ملی و روز عبور خود را وارد نمایید",
            type: "success",
            confirmButtonText: "Ok",
          }).then((r) => {
            console.log(r.value);
          });
          this.$router.push("/login");
        })
        .catch(() => {
          this.$fire({
            title: "Error !",
            text: "The information entered is duplicate or incorrect",
            type: "error",
            confirmButtonText: "try again",
          }).then((r) => {
            console.log(r.value);
          });
        });
    },
  },
};
</script>

<style scoped>
.inpute-all {
  border: 0;
  border-bottom: 1px solid #000;
  outline: 0;
  font-size: 16px;
  background: transparent;
  width: 100%;
  letter-spacing: 0.125rem;
  transition: all 0.5s cubic-bezier(0.4, 0.25, 0.8, 0.3);
}
</style>
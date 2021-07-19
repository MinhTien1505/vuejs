<template>
  <v-app>
    <v-main>
      <div class="contain">
        <h1 class="text-center mt-5">Login</h1>
        <v-form ref="form" v-model="valid" lazy-validation>
          <v-text-field
            v-model="name"
            :counter="10"
            :rules="nameRules"
            label="Name"
            required
          ></v-text-field>

          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            required
          ></v-text-field>

          <v-btn color="success" class="mr-4 mt-5">
            Login
          </v-btn>

          <v-btn color="primary" class="mt-5">
            Register
          </v-btn>
        </v-form>
      </div>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    name: "",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => (v && v.length <= 10) || "Name must be less than 10 characters",
    ],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
  }),
};
</script>

<style>
.contain {
  width: 50%;
  margin: 0 auto;
}
</style>

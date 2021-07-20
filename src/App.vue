<template>
  <div id="app">
    <v-app>
      <v-app-bar app color=" accent-4" dense>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-toolbar-title>Page title</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
        <v-btn>
          <router-link to="/login">Login</router-link>
        </v-btn>
        <v-btn>
          <router-link to="/dashboard">Dashboard</router-link>
        </v-btn>

        <v-menu left bottom>
          <template v-slot:activator="{ on, attrs }">
            <v-btn icon v-bind="attrs" v-on="on">
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
          </template>

          <v-list>
            <v-list-item v-for="n in 5" :key="n" @click="() => {}">
              <v-list-item-title>Option {{ n }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-app-bar>

      <router-view />
    </v-app>
  </div>

  <!-- <v-app>
    <Dashboard />
  </v-app> -->
</template>

<script>
// import Dashboard from "./components/Dashboard.vue";
// import Login from "./components/Login.vue";

export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>

<style scoped>
.contain {
  width: 50%;
  margin: 0 auto;
}
</style>

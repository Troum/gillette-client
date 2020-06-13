<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
    </v-app-bar>
    <v-main>
      <router-view></router-view>
    </v-main>
    <alert-component/>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data(){
    return {

    }
  }
};
</script>

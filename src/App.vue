<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>CHRIS</span>
        <span class="font-weight-light">CARLSON</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Full Stack Developer</span>
      </v-btn>
    </v-app-bar>

    <v-content>
      <HomeComponent/>
    </v-content>
  </v-app>
</template>

<script>
import HomeComponent from './components/HomeComponent';

export default {
  name: 'App',
  components: {
    HomeComponent,
  },
  data: () => ({
    //
  }),
};
</script>

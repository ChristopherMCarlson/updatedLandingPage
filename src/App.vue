<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="text-uppercase" :class="[$vuetify.breakpoint.mdAndDown ? 'caption' : 'headline']">
        <span>CHRIS</span>
        <span class="font-weight-light">CARLSON</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
        <span  :class="[$vuetify.breakpoint.mdAndDown ? 'caption' : 'headline']" class="font-weight-medium">Full Stack Developer</span>
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

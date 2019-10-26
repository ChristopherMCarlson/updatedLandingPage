<template>
  <v-container>
    <v-row style="height: 70vh" align="center">
      <v-col cols="12">
        <v-row class='d-flex justify-center'>
          <p :class="[$vuetify.breakpoint.mdAndDown ? 'display-1' : 'display-4']">Hi, I'm Chris!</p>
        </v-row>
        <v-row class='d-flex justify-center'>
          <p :class="[$vuetify.breakpoint.mdAndDown ? 'caption' : 'display-1']">Full Stack Developer | CSS Enthusiast | Dad Joke Lover</p>
        </v-row>
        <v-row class='d-flex justify-center'>
          <v-col class="text-center" :cols="[$vuetify.breakpoint.mdAndDown ? 2 : 1]"
          v-for="icon in icons"
          :key="icon">
            <v-tooltip bottom>
              <template v-slot:activator="{ on }">
                <v-hover v-slot:default="{ hover }">
                  <v-icon
                  :href="icon.link"
                  :size="[$vuetify.breakpoint.mdAndDown ? 50 : 75]"
                  tag="a"
                  target="_blank"
                  style="text-decoration: none;"
                  :color="hover ? 'blue' : 'grey'"
                  v-on="on">{{icon.icon}}</v-icon>
                </v-hover>
              </template>
              <span>{{icon.name}}</span>
            </v-tooltip>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    icons: [
      {
        icon: 'fab fa-github fa-5x',
        link: 'https://github.com/ChristopherMCarlson',
        name: 'Github'
      },
      {
        icon: 'fab fa-linkedin fa-5x',
        link: 'https://www.linkedin.com/in/christopher-carlson-303953163/',
        name: 'LinkedIn'
      },
      {
        icon: 'fab fa-twitter fa-5x',
        link: 'https://twitter.com/C_M_Carlson',
        name: 'Twitter'
      },
      {
        icon: 'fas fa-folder fa-5x',
        link: 'https://cmcinspire.herokuapp.com/#/main',
        name: 'Portfolio'
      },
      {
        icon: 'fas fa-file fa-5x',
        link: 'https://docs.google.com/document/d/19JO6IoMKg1Fyhq4Tli8sAsapy7Ds-EGa5JL3VC-NEFk/edit?usp=sharing',
        name: 'Resume'
      }
    ]
  })
};
</script>

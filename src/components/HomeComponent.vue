<template>
  <v-container>
    <v-row style="height: 70vh" align="center">
      <v-col cols="12">
        <v-row class='d-flex justify-center'>
          <h1>Hi, I'm Chris!</h1>
        </v-row>
        <v-row class='d-flex justify-center'>
          <h3>Full Stack Developer | CSS Enthusiast | Material Designer</h3>
        </v-row>
        <v-row class='d-flex justify-center'>
          <v-col class="text-center" cols="1"
          v-for="icon in icons"
          :key="icon">
            <v-hover v-slot:default="{ hover }">
              <v-icon
              :href="icon.link"
              size="100"
              tag="a"
              target="_blank"
              style="text-decoration: none;"
              :color="hover ? grey : blue">{{icon.icon}}</v-icon>
            </v-hover>
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
      link: 'https://github.com/ChristopherMCarlson'
    },
    {
      icon: 'fab fa-linkedin fa-5x',
      link: 'https://www.linkedin.com/in/christopher-carlson-303953163/'
    },
    {
      icon: 'fab fa-twitter fa-5x',
      link: 'https://twitter.com/C_M_Carlson'
    },
    {
      icon: 'fas fa-folder fa-5x',
      link: 'https://cmcinspire.herokuapp.com/#/main'
    },
    {
      icon: 'fas fa-file fa-5x',
      link: 'https://docs.google.com/document/d/19JO6IoMKg1Fyhq4Tli8sAsapy7Ds-EGa5JL3VC-NEFk/edit?usp=sharing'
    }
    ]
  }),
};
</script>

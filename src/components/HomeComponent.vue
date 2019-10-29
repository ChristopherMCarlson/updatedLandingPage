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
            <v-tooltip bottom :disabled="$vuetify.breakpoint.mdAndDown">
              <template v-slot:activator="{ on }">
                <v-hover v-slot:default="{ hover }">
                  <v-icon
                  :href="icon.link"
                  :size="[$vuetify.breakpoint.mdAndDown ? 50 : 75]"
                  tag="a"
                  target="_blank"
                  style="text-decoration: none;"
                  :color="hover ? 'blue' : 'grey'"
                  v-on="on"
                  >{{icon.icon}}</v-icon>
                </v-hover>
              </template>
              <span>{{icon.name}}</span>
            </v-tooltip>
          </v-col>
          <v-col class="text-center" :cols="[$vuetify.breakpoint.mdAndDown ? 2 : 1]">
            <v-tooltip bottom :disabled="$vuetify.breakpoint.mdAndDown">
              <template v-slot:activator="{ on }">
                <v-hover v-slot:default="{ hover }">
                  <v-icon
                  :size="[$vuetify.breakpoint.mdAndDown ? 50 : 75]"
                  tag="a"
                  target="_blank"
                  style="text-decoration: none;"
                  :color="hover ? 'blue' : 'grey'"
                  v-on="on"
                  @click.prevent="resumeDialog=true"
                  >fas fa-file fa-5x</v-icon>
                </v-hover>
              </template>
              <span>Resume</span>
            </v-tooltip>
          </v-col>
          <v-col class="text-center" :cols="[$vuetify.breakpoint.mdAndDown ? 2 : 1]">
            <v-tooltip bottom :disabled="$vuetify.breakpoint.mdAndDown">
              <template v-slot:activator="{ on }">
                <v-hover v-slot:default="{ hover }">
                  <v-icon
                  :size="[$vuetify.breakpoint.mdAndDown ? 50 : 75]"
                  tag="a"
                  target="_blank"
                  style="text-decoration: none;"
                  :color="hover ? 'blue' : 'grey'"
                  v-on="on"
                  @click.prevent="dialog=true"
                  >fas fa-folder fa-5x</v-icon>
                </v-hover>
              </template>
              <span>Portfolio</span>
            </v-tooltip>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-dialog v-model="resumeDialog" fullscreen hide-overlay transition="dialog-bottom-transition" scrollable>
      <v-card>
        <v-toolbar>
          <v-btn icon dark @click="resumeDialog = false">
            <v-icon color='grey'>mdi-close</v-icon>
          </v-btn>
          <v-toolbar-title>Resume</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-toolbar-items>
            <v-btn color="blue" text @click="resumeDialog = false">Download</v-btn>
          </v-toolbar-items>
        </v-toolbar>
        <v-row class='mx-0'>
          <Resume/>
        </v-row>
      </v-card>
    </v-dialog>
    <v-dialog v-model="dialog" fullscreen hide-overlay transition="dialog-bottom-transition">
      <v-card>
        <v-toolbar>
          <v-btn icon dark @click="dialog = false">
            <v-icon color='grey'>mdi-close</v-icon>
          </v-btn>
          <v-toolbar-title>Portfolio</v-toolbar-title>
        </v-toolbar>
        <v-row class='mx-0'>
          <v-col
          v-for="project in portfolio"
          :key="project"
          :cols="[$vuetify.breakpoint.mdAndDown ? 12 : 4]"
          >
          <v-card v-if='$vuetify.breakpoint.mdAndDown' class='mx-2'>
              <div class="d-flex flex-no-wrap justify-space-between">
                  <div>
                    <v-card-title
                      class="headline"
                      v-text="project.name"
                    ></v-card-title>
    
                    <v-card-subtitle v-text="project.used"></v-card-subtitle>
                    <v-card-actions>
                        <v-btn text :href="project.link" target="_blank">View</v-btn>
                        <v-btn color="purple" text>
                          Explore
                        </v-btn>
                      </v-card-actions>
                  </div>
                  <v-avatar
                    class="ma-3"
                    size="125"
                    tile
                  >
                    <v-img :src="project.src"></v-img>
                  </v-avatar>
                </div>
          </v-card>
          <v-card class="mx-auto" max-width="344" v-else>
            <v-img
              :src="project.src"
              height="200px"
            ></v-img>
            <v-card-title>
              {{project.name}}
            </v-card-title>
            <v-card-subtitle>
              {{project.used}}
            </v-card-subtitle>
            <v-card-actions>
              <v-btn text :href="project.link" target="_blank">View</v-btn>
              <v-btn color="purple" text>
                Explore
              </v-btn>
            </v-card-actions>
            <v-expand-transition>
              <div v-show="show">
                <v-divider></v-divider>
                <v-card-text>
                  {{project.desc}}
                </v-card-text>
              </div>
            </v-expand-transition>
            </v-card>
          </v-col>
        </v-row>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
import Resume from './Resume';

export default {
  components: {
    Resume,
  },
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
      }
    ],
    dialog: false,
    resumeDialog: false,
    portfolio: [
    {
      name: 'Lendr',
      desc: 'An app designed to ease lending items to friends, built using VueJS and Vuetify, server built using NodeJS',
      used: 'VueJS, Vuetify, NodeJS',
      link: 'http://lendr-app.herokuapp.com/#/',
      color: 'white',
      src: require('@/assets/lenderApp.png'),
      show: false
    },
    {
      name: 'Insipre',
      desc: 'A landing page designed to help keep track of a to do list, serve the weather based on user input location, and display random pictures based on the Unsplash API, built using VueJS and Vuetify, server built using NodeJS',
      used: 'VueJS, Vuetify, NodeJS',
      link: 'https://cmcinspire.herokuapp.com/#/',
      color: 'white',
      src: require('@/assets/inspireApp.png'),
      show: false
    }
    ]
  })
};
</script>

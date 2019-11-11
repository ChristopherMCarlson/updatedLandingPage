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
    <v-row justify="center">
      <v-dialog v-model="resumeDialog" fullscreen hide-overlay="true" transition="dialog-bottom-transition" scrollable="true">
        <v-card>
          <v-toolbar elevation='0'>
            <v-btn icon dark @click="resumeDialog = false">
              <v-icon color='grey'>mdi-close</v-icon>
            </v-btn>
            <v-toolbar-title>Resume</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items>
              <v-btn color="blue" text @click="resumeDialog = false">Download</v-btn>
            </v-toolbar-items>
          </v-toolbar>
          <v-card-text class='mt-3 justify-center resume-padding'>
            <p class="text-center display-1">Christopher Carlson</p>
            <hr/>
            <v-row>
              <v-col cols="12">
                <v-row class='d-flex justify-space-between'>
                  <p>c.m.carlson13@gmail.com</p>
                  <p>208-813-5288</p>
                </v-row>
              </v-col>
            </v-row>
            <p class="text-center headline">SOFTWARE ENGINEER</p>
            <p class="text-left body-1">A US Army veteran with experience in front and back-end software development technologies. Passionate about innovation, problem solving and building applications with an emphasis on client functionality. Recently completed an immersive coding program, challenged and grew in programming and scrum skills. A goal setter, natural born leader and possesses excellent collaboration and project coordinating abilities. Seeking an opportunity with a leading tech company focused on connecting users with creative breakthrough applications.</p>
            <v-row class='d-flex justify-space-between'>
              <p class="subtitle-1 font-weight-medium">Innovative Software Engineer</p>
            </v-row>
            <v-list disabled>
              <v-list-item-content>
                <p class='body-1'>Offering experience in the full software development lifecycle- from concept through delivery of applications and customizable solutions.</p>
              </v-list-item-content>
            </v-list>
            <v-row class='d-flex justify-space-between'>
              <p class="subtitle-1 font-weight-medium">Experienced in development methodologies,</p>
            </v-row>
            <v-list disabled>
              <v-list-item-content>
                <p class='body-1'>tools and processes contributing to the design and rollout of software applications.</p>
              </v-list-item-content>
            </v-list>
            <v-row class='d-flex justify-space-between'>
              <p class="subtitle-1 font-weight-medium">Known for excellent troubleshooting skills</p>
            </v-row>
            <v-list disabled>
              <v-list-item-content>
                <p class='body-1'>Able to analyze code and engineer well-researched responsive solutions.</p>
              </v-list-item-content>
            </v-list>
            <hr/>
          <p class="text-center headline">PROFESSIONAL EXPERIENCE</p>
          <v-row class='d-flex justify-space-between'>
            <p class="subtitle-1 font-weight-medium">Junior Software Engineer, Verified First</p>
            <p class="subtitle-1 font-weight-medium">11/2018-Present</p>
          </v-row>
          <v-list disabled>
            <v-list-item-content>
              <p class='body-1'>&#8226; Part of a three person development team in charge of internal software development.</p>
              <p class='body-1'>&#8226; Met with internal employees to discover, plan, and develop solutions to optimize workflow</p>
              <p class='body-1'>&#8226; Conducted QA for internal design and development</p>
              <p class='body-1'>&#8226; Administered hotfixes to ensure smooth daily operations</p>
              <p class='body-1'>&#8226; Served as a thought partner for the Director of Information Systems</p>
              <p class='body-1'>&#8226; Programmed back-end and front-end code within SalesForce</p>
            </v-list-item-content>
          </v-list>
          <v-row class='d-flex justify-space-between'>
              <p class="subtitle-1 font-weight-medium">Full Stack Developer Student, CodeWorks</p>
              <p class="subtitle-1 font-weight-medium">07/2018-10/2018</p>
            </v-row>
            <v-list disabled>
              <v-list-item-content>
                <p class='body-1'>&#8226; Completed over 500 hours of software development in an immersive learning environment.</p>
                <p class='body-1'>&#8226; Participated in 24-hour hack-a-thons events testing and challenging personal goals.</p>
                <p class='body-1'>&#8226; Designed a music playlist app (Vue Music) where users search and add favorite artists to personalized lists. Integrated with iTunes Api, and built with VueJS.</p>
                <p class='body-1'>&#8226; Utilized VueJS, node, and Vuetify to develop a user dashboard app displaying current weather, time, and rotating quotes and images.</p>
                <p class='body-1'>&#8226; Collaborated on group capstone project (Lendr), created an app to track status of loaned items to other users and allowed users to confirm receipt of lent items with attached due dates. Developed with VueJS, Vuetify, and Socket.io.</p>
                <p class='body-1'>&#8226; Collaborated on a group project (Post-It) during 24-hour hack-a-thon to create a messaging board that allowed users to create accounts, start discussion threads, comment on threads, and provide feedback on comments and posts via a voting system.</p>
                <p class='body-1'>&#8226; Spent time learning Vuetify for VueJS in order to better style web apps.</p>
              </v-list-item-content>
            </v-list>
            <v-row class='d-flex justify-space-between'>
              <p class="subtitle-1 font-weight-medium">Biller, Saia LTL Freight</p>
              <p class="subtitle-1 font-weight-medium">04/2014-04/2018</p>
            </v-row>
            <v-list disabled>
              <v-list-item-content>
                <p class='body-1'>&#8226; Maintained private billing information and verified customer accounts through security protocols and procedures.</p>
                <p class='body-1'>&#8226; Identified errors in customer processing forms, and ensured accurate adjustments were applied to prevent freight delays.</p>
              </v-list-item-content>
            </v-list>
            <v-row class='d-flex justify-space-between'>
              <p class="subtitle-1 font-weight-medium">Fire Support Specialist, US Army</p>
              <p class="subtitle-1 font-weight-medium">07/2011-07/2014</p>
            </v-row>
            <v-list disabled>
              <v-list-item-content>
                <p class='body-1'>&#8226; Received promotion and awarded Army Achievement Medal for excellent driving of a specialized vehicle.</p>
                <p class='body-1'>&#8226; Honored Commendations: Army Service Ribbon, Global War on Terror Service Medal, National Defense Service.</p>
                <p class='body-1'>&#8226; Managed transportation and communication efforts for armored vehicles and ensuring safe drivable conditions.</p>
                <p class='body-1'>&#8226; Utilized understanding of advanced math to guarantee accuracy of quick calculations and prevent errors.</p>
              </v-list-item-content>
            </v-list>
            <hr/>
            <p class="text-center headline">EDUCATION</p>
            <v-row class='d-flex justify-space-between'>
                <p class="subtitle-1 font-weight-medium">Certificate of Completion, Boise Code Works</p>
                <p class="subtitle-1 font-weight-medium">2018</p>
              </v-row>
          </v-card-text>
        </v-card>
      </v-dialog>
    </v-row>
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

<style>
  .resume-padding{
    padding: 0% 25% 0% 25% !important;
  }

  @media only screen and (min-device-width : 320px) and (max-device-width : 480px) {
      .resume-padding{
      padding: 0% 5% 0% 5% !important;
      }
    }
</style>

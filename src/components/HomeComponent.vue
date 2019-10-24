<template>
  <v-container>
    <v-row style="height: 70vh" align="center">
      <v-col cols="12">
        <v-row>
          <h1>Hi, I'm Chris!</h1>
        </v-row>
        <v-row>
          <h3>Full Stack Developer | CSS Enthusiast | </h3>
        </v-row>
        <v-row>
          <v-col class="text-center" cols="1"
          v-for="icon in icons"
          :key="icon">
            <i :class="icon"></i>
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
    'fab fa-github fa-5x',
    'fab fa-linkedin fa-5x',
    'fab fa-twitter fa-5x',
    'fas fa-folder-open fa-5x',
    'fas fa-file fa-5x'
    ]
  }),
};
</script>

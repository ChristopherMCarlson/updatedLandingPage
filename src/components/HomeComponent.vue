<template>
  <v-container>
    <v-row style="height: 70vh" align="center">
      <v-col justify-content="center" cols="1"
      v-for="icon in icons"
      :key="icon">
        <i :class="icon"></i>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    icons: [
    'fab fa-github fa-5x',
    'fab fa-github fa-5x',
    'fab fa-github fa-5x',
    'fab fa-github fa-5x',
    'fab fa-github fa-5x',
    'fab fa-github fa-5x'
    ]
  }),
};
</script>

<template>
  <v-app dark>
    <v-app-bar fixed app>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-toolbar-items class="hidde-sm-and-down">
        <v-btn text>
          <nuxt-link to="/weather-app"> Weather app </nuxt-link>
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: 'Weather',
    }
  },
}
</script>

<style scoped>
a {
  text-decoration: none;
  color: rgb(251, 247, 247);
}
</style>

<!--
     Author:    Build Rise Shine with Nyros (BRS) 
     Created:   11.05.2022 
     Library / Component: Default layout
     Description: Displays  the layout for the app which is like a component 
     (c) Copyright by BRS with Nyros. 
-->
<template>
  <v-app>
    <v-app-bar fixed app>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-toolbar-items class="hidde-sm-and-down">
        <v-btn text>
          <nuxt-link to="/weather-app"> Home </nuxt-link>
        </v-btn>
        <v-btn text>
          <nuxt-link to="/about"> ABOUT API </nuxt-link>
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
.theme--dark.v-application {
  background: white !important;
  color: #ffffff;
}
</style>

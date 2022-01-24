<!--
     Author:    Build Rise Shine with Nyros (BRS) 
     Created:   11.05.2022 
     Library / Component: Weather componenet
     Description: Page displays a input field to search for the weather details witha a button
     (c) Copyright by BRS with Nyros. 
-->
<template>
  <v-container>
    <v-flex>
      <v-card color="dark-grey darken-2">
        <v-card-text>
          <v-layout class="justify-center">
            <v-flex v-if="weather.weather" class="text-xs-center">
              <h4>Temperature</h4>
              <h1>{{ weather.name }}</h1>
              <img :src="icon" alt="weather icon" />
              <p>
                <span class="display-1">{{ temp() }} &deg;C</span>
                <span class="caption">{{
                  weather.weather[0].description
                }}</span>
              </p>
            </v-flex>
          </v-layout>
        </v-card-text>
      </v-card>
    </v-flex>
    <v-flex xs12 class="mt-4">
      <v-form @submit.prevent="getWeatherInfo">
        <v-text-field
          v-model="city"
          label="Enter city name"
          outlined
          rows="1"
          row-height="15"
          solo
        ></v-text-field>
        <v-btn @click="getWeatherInfo">Submit</v-btn>
      </v-form>
    </v-flex>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      city: 'Kakinada',
      weather: {},
    }
  },
  computed: {
    icon() {
      return this.weather.weather
        ? `https://openweathermap.org/img/w/${this.weather.weather[0].icon}.png`
        : ''
    },
  },
  created() {
    this.getWeatherInfo()
  },
  methods: {
    getWeatherInfo() {
      this.$axios
        .$get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=6970920ec1201b03b6906b18ce5d7dbb`
        )
        // eslint-disable-next-line no-console
        .then((res) => (this.weather = res))
    },
    temp() {
      return this.weather.main ? Math.round(this.weather.main.temp - 273) : ''
    },
  },
  head() {
    return {
      title: 'Weather app',
    }
  },
}
</script>

<style lang="stylus" scoped></style>

<template>
  <div class="home">
    <WeatherList tagline="Weather in London" v-bind:weather="weather" />
  </div>
</template>

<script>
import WeatherList from "../components/WeatherList";
export default {
  name: "Home",
  components: {
    WeatherList,
  },
  data() {
    return {
      weather: [],
    };
  },
  created() {
    this.weather = ["hello", "weather"];
    // console.log(this.weather);
  },
};
</script>

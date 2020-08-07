<template>
  <div>
    <h3>{{ tagline }}</h3>
    <div class="weatherList" v-bind:key="item.dt" v-for="item in weather">
      <WeatherItem v-bind:item="item" />
    </div>
  </div>
</template>
<script>
import WeatherItem from "./WeatherItem";
export default {
  name: "WeatherList",
  components: {
    WeatherItem,
  },
  props: {
    tagline: String,
    weather: Array,
  },
};
</script>
<style scoped>
h3 {
  font-weight: normal;
  font-style: italic;
}
</style>

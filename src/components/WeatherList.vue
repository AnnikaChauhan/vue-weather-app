<template>
  <div>
    <h3>{{ tagline }}</h3>
    <div class="weatherList">
      <WeatherItem
        v-for="item in weather"
        v-bind:item="item"
        v-bind:key="item.dt"
      />
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
.weatherList {
  padding: 20px;
  margin: 20px;
  background: rgba(44, 62, 80, 0.5);
  border: 1px solid rgb(44, 62, 80);
  border-radius: 6px;
}
</style>

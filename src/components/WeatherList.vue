<template>
  <div>
    <h3>{{ tagline }}</h3>
    <div class="weatherList">
      weather list
    </div>
  </div>
</template>
<script>
export default {
  name: "WeatherList",
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

<template>
  <div id="weatherItem">
    <p>{{ this.convertUtcToDay(item.dt) }}</p>
    <p>{{ this.convertKelvinToCelsius(item.main.temp) }}&deg;</p>
  </div>
</template>
<script>
export default {
  name: "WeatherItem",
  props: ["item"],
  methods: {
    convertKelvinToCelsius(kelvin) {
      const celsius = Number.parseFloat(kelvin - 273.15).toFixed(0);
      return celsius;
    },
    convertUtcToDay(utc) {
      let utcDate = new Date(utc * 1000);
      let date = utcDate.toGMTString();
      let day = date.substring(0, 3);
      return day;
    },
  },
};
</script>
<style>
#weatherItem {
  font-size: 25px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  background: white;
  margin: 5px 0;
  padding: 10px;
  border-radius: 6px;
}
</style>

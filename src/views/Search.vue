<template>
  <div class="home">
    <div>
      <input
        type="text"
        name="search"
        id="search"
        placeholder="Search.."
        v-model="city"
      />
      <button v-on:click="search">Search</button>
    </div>
    <WeatherList
      tagline="Search the weather in another City"
      v-bind:weather="weather"
    />
  </div>
</template>

<script>
import axios from "axios";
import WeatherList from "../components/WeatherList";
export default {
  name: "Home",
  components: {
    WeatherList,
  },
  data() {
    return {
      weather: [],
      city: "",
      appid: "0a30e476b278414999f2fa1f9e2e6e38",
    };
  },
  created() {
    const weatherURL = `https://api.openweathermap.org/data/2.5/forecast?q=${this.city}&appid=${this.appid}`;
    axios
      .get(weatherURL)
      .then(
        (response) =>
          (this.weather = response.data.list.filter(
            (item) => response.data.list.indexOf(item) % 8 === 0
          ))
      )
      .catch((error) => console.log(error));
  },
  methods: {
    search: function() {
      console.log(this.city);
    },
  },
};
</script>

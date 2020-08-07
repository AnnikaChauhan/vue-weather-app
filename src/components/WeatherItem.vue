<template>
  <div>
    Weather
    <p>{{ item.main.temp }}</p>
  </div>
</template>
<script>
export default {
  name: "WeatherItem",
  props: ["item"],
};
</script>

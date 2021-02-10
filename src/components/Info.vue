<template>
  <div
    v-if="
      typeof weatherInfo.current && typeof weatherInfo.location != 'undefined'
    "
  >
    <div class="feelslike">
      {{ weatherInfo.location.country }}
    </div>
    <div class="feelslike">
      {{ weatherInfo.location.localtime }}
    </div>
    <div class="condition">
      Condition:{{ weatherInfo.current.condition.text }}
    </div>
    <div class="temp">
      Current temprature : {{ Math.round(weatherInfo.current.temp_c) }}
    </div>

    <div class="feelslike">
      Feels like : {{ Math.round(weatherInfo.current.feelslike_c) }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Info",
  props: {
    weatherInfo: Object
  }
};
</script>

<style></style>

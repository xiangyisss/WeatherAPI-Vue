<template>
  <div>
    <input
      type="text"
      placeholder="Which City?"
      v-model="cityName"
      @keyup.enter="getDataForCity"
    />
    <info :weatherInfo="weatherInfo" />
  </div>
</template>

<script>
import axios from "axios";
import Info from "@/components/Info.vue";

export default {
  name: "Home",
  components: {
    Info
  },
  data() {
    return {
      cityName: "",
      weatherInfo: {}
    };
  },
  methods: {
    getDataForCity() {
      axios
        .get(
          `http://api.weatherapi.com/v1/current.json?key=5178f06d177f46eab3302501211201&q=${this.cityName}`
        )
        .then(res => {
          this.weatherInfo = res.data;
        })
        .catch(err => {
          console.log(err);
        });
    }
  }
};
</script>

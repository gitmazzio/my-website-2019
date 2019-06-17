<template>
  <div class="row ml-1 mr-1">
    <div class="col-sm-6 img__iphone--weather">
      <img src="img/iphone-weather.png" alt>
    </div>
    <div class="col-sm-6 m-auto">
      <MainTitle msg="Weather UI"/>
      <p>Weather React app with stateless functional components</p>
      <b-button
        href="http://weather.matteomazziotti.it"
        target="_blank"
        variant="primary"
        class="sticky-bottom mt-2"
      >Demo</b-button>
      <b-button
        href="https://github.com/gitmazzio/weather-UI"
        target="_blank"
        variant="success"
        class="sticky-bottom mt-2 ml-2"
      >GitHub Repo</b-button>
    </div>
  </div>
</template>

<script>
import MainTitle from "./MainTitle.vue";

export default {
  components: {
    MainTitle
  }
};
</script>

<style>
.img__iphone--weather {
  text-align: right;
}
.img__iphone--weather img {
  width: 60%;
  height: auto;
}

@media screen and (max-width: 575px) {
  .img__iphone--weather {
    text-align: center;
  }
  .img__iphone--weather img {
    width: 70%;
    height: auto;
  }
}
</style>

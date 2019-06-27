<template>
  <div class="row">
    <div class="col-sm-4">
      <img
        :src="require('../assets/me.png')"
        alt
        class="myPictures img__rounded"
      >
    </div>

    <div class="col-sm-8 mt-5">
      <MainTitle msg="Hey!" moreClasses="title--big font-weight-bold"/>
      <p class="font-weight-bold">
        I'm Matteo Mazziotti
        <br>I'm a creative Front-end Developer
      </p>
      <b-badge class="p-2 m-1" variant="dark">26 years old</b-badge>
      <b-badge class="p-2 m-1" variant="warning">Milan</b-badge>
      <b-badge class="p-2 m-1" variant="danger">Front-end Dev</b-badge>
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
.myPictures {
  width: 100%;
  margin-left: 5em;
}
.img__rounded {
  border-radius: 50%;
}

@media only screen and (max-width: 575px) {
  .myPictures {
    width: 50%;
    margin: 0;
  }
}
</style>

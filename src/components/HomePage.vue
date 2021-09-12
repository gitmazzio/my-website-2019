<template>
  <div class="row">
    <div class="col-sm-4">
      <img
        :src="require('../assets/me.png')"
        alt
        class="myPicture img__rounded"
      />
    </div>

    <div class="col-sm-8 mt-5">
      <MainTitle msg="Hey!" moreClasses="title--big font-weight-bold" />
      <p class="font-weight-bold">
        I'm Matteo Mazziotti
        <br />I'm a creative Front-end Developer
      </p>
      <b-badge class="p-2 m-1" variant="dark">{{ `${age} years old` }}</b-badge>
      <b-badge class="p-2 m-1" variant="warning">Milan</b-badge>
      <b-badge class="p-2 m-1" variant="danger">Front-end Dev</b-badge>
    </div>
  </div>
</template>

<script>
import MainTitle from "./MainTitle.vue";
import moment from "moment";

export default {
  data() {
    return {
      age: Math.floor(
        moment().diff(moment("20011993", "DDMMYYYY")) /
          (365 * 60 * 60 * 24 * 1000)
      ),
    };
  },
  components: {
    MainTitle,
  },
};
</script>

<style>
.myPicture {
  width: 100%;
  margin-left: 5em;
}
.img__rounded {
  border-radius: 50%;
}

@media only screen and (max-width: 575px) {
  .myPicture {
    width: 50%;
    margin: 0;
  }
}
</style>

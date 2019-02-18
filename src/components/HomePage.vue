<template>
  <div class="row">
    <div class="col-sm-4">
      <img :src="require('../assets/me.png')" alt class="myPictures img__rounded img__shadow">
    </div>

    <div class="col-sm-8 mt-5">
      <MainTitle msg="Hi" moreClasses="title--big"/>
      <p>
        I'm Matteo Mazziotti<br />
        I'm a creative front-end developer
      </p>
      <b-badge class="p-2 m-1" variant="dark">26 years old</b-badge>
      <b-badge class="p-2 m-1"  variant="warning">Milan</b-badge>
      <b-badge class="p-2 m-1"  variant="danger">Front-end dev</b-badge>
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
.img__shadow {
  -webkit-box-shadow: 10px 10px 72px -10px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 10px 10px 72px -10px rgba(0, 0, 0, 0.75);
  box-shadow: 10px 10px 72px -10px rgba(0, 0, 0, 0.75);
}

@media only screen and (max-width: 575px) {
  .myPictures {
  width: 50%;
  margin: 0;
}
}

@media print {
  .row {
    
  }
}
</style>

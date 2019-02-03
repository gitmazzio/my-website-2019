<template>
  <div>
    <MainTitle msg="Contacts"/>
    <button v-clipboard:copy="email"></button>
    <b-button
      v-clipboard:copy="email"
      variant="secondary"
      class="sticky-bottom"
      v-b-tooltip.click
          title="Copied!"
    >
      <span>copy &#128517;</span>
    </b-button>
  </div>
</template>

<script>
import MainTitle from "./MainTitle.vue";

export default {
  data() {
    return {
      email: "mmazziotti1@gmail.com"
    };
  },
  components: {
    MainTitle
  }
};
</script>

<style>
</style>

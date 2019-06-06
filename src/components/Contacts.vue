<template>
  <div>
    <MainTitle msg="Contacts"/>
    <span>
      Don't hesitate to contact me at
      <p>
        <a href="mailto:mmazziotti1@gmail.com">mmazziotti1@gmail.com</a>
      </p>
    </span>
  </div>
</template>

<script>
import MainTitle from "./MainTitle.vue";

export default {
  data() {
    return {
      email: "mmazziotti1@gmail.com",
      textCopied: "Copy!"
    };
  },
  components: {
    MainTitle
  },
  methods: {
    handleCopyStatus(status) {
      if (status) {
        this.textCopied = "Copied!";
      }
    }
  }
};
</script>

<style scoped>
p a {
  font-size: 1.5rem;
  color: var(--mail-color);
}

@media screen and (max-width: 575px) {
  p a {
    font-size: 1.1rem;
    color: white;
  }
}
</style>

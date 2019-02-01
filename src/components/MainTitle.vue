<template>
  <h1 :class="'title--big '+ moreClasses" :style="'color: '+ color">&lt;{{ msg }} /&gt;</h1>
</template>

<script>
export default {
  props: {
    msg: String,
    moreClasses: String,
    color: String
  }
};
</script>

<style>
.title--big {
  font-size: 5rem;
}
</style>

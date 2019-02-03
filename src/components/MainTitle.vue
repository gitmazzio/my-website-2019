<template>
  <div class="typewriter">
    <h1 :class="'title--big '+moreClasses" :style="'color: '+ color">&lt;{{ msg }} /&gt;</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg_length: this.msg.length
    };
  },
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
.typewriter {
  width: fit-content;
  margin: auto;
}

.typewriter h1 {
  overflow: hidden; /* Ensures the content is not revealed until the animation */
  border-right: 0.15em solid orange; /* The typwriter cursor */
  white-space: nowrap; /* Keeps the content on a single line */
  margin: 0 auto; /* Gives that scrolling effect as the typing happens */
  letter-spacing: 0.15em; /* Adjust as needed */
  animation: 
    typing 2.5s steps(30, end),
    blink-caret 1s step-end infinite;
}

/* The typing effect */
@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}

/* The typewriter cursor effect */
@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }
  50% {
    border-color: white;
  }
}
</style>

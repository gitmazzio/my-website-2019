<template>
  <div class="typewriter">
    <h1 :class="moreClasses" :style="'color: '+ color">&lt;{{ msg }} /&gt;</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg_length: this.msg.length,
    };
  },
  props: {
    msg: String,
    moreClasses: String,
    color: String,
  },
};
</script>

<style>
.title--big {
  font-size: 5rem !important;
}

.typewriter {
  width: fit-content;
  margin: auto;
}

.typewriter h1 {
  font-size: 3rem;
  overflow: hidden; /* Ensures the content is not revealed until the animation */
  border-right: 0.15em solid orange; /* The typwriter cursor */
  white-space: nowrap; /* Keeps the content on a single line */
  margin: 0 auto; /* Gives that scrolling effect as the typing happens */
  letter-spacing: 0.15em; /* Adjust as needed */
  animation: typing 2.5s steps(30, end), blink-caret 1s step-end infinite;
}

@media screen and (max-width: 575px) {
  .typewriter h1 {
    font-size: 1.8rem;
  }

  .title--big {
    font-size: 2.3rem !important;
  }
}

@media screen and (max-width: 320px) {
  .typewriter h1 {
    font-size: 1.2rem;
  }

  .title--big {
    font-size: 1.7rem !important;
  }
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

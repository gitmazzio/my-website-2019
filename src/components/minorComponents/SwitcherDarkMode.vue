<template>
  <div class="theme-switch-wrapper" v-b-tooltip.hover title="Dark Mode">
    <label class="theme-switch" for="checkbox">
      <input type="checkbox" id="checkbox">
      <div class="slider round"></div>
    </label>
  </div>
</template>

<script>
export default {
  mounted() {
    const toggleSwitch = document.querySelectorAll(
      '.theme-switch input[type="checkbox"]'
    );

    toggleSwitch.forEach(elem => {
      elem.addEventListener(
        "change",
        e => {
          if (e.target.checked) {
            document.documentElement.setAttribute("data-theme", "dark");
          } else {
            document.documentElement.setAttribute("data-theme", "light");
          }
        },
        false
      );
    });
  },
  methods: {
    switchTheme(e) {
      console.log("ciao");
      if (e.target.checked) {
        document.documentElement.setAttribute("data-theme", "dark");
      } else {
        document.documentElement.setAttribute("data-theme", "light");
      }
    }
  }
};
</script>

<style>
.theme-switch-wrapper {
  display: flex;
  align-items: center;
}

.theme-switch-wrapper em {
  margin-left: 10px;
  font-size: 1rem;
}

.theme-switch {
  display: inline-block;
  height: 23px;
  position: relative;
  width: 52px;
  top: 6px;
}

.theme-switch input {
  display: none;
}

.slider {
  background-color: #ccc;
  bottom: 0;
  cursor: pointer;
  left: 0;
  position: absolute;
  right: 0;
  top: 0;
  transition: 0.4s;
}

.slider:before {
  background-color: #fff;
  bottom: 2px;
  content: "";
  height: 19px;
  width: 19px;

  left: 4px;
  position: absolute;
  transition: 0.4s;
}

input:checked + .slider {
  background-color: #66bb6a;
}

input:checked + .slider:before {
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
</style>

<template>
  <div id="app">
    <span id="logo" class="logo">MM</span>
    <MainMenu/>
    <HamburgerMenu/>
    <full-page :options="options" id="fullpage" ref="fullpage">
      <div class="section" id="section1">
        <HomePage/>
      </div>
      <div class="section" id="section2">
        <div class="slide" data-anchor="/me">
          <MainTitle msg="About me"/>
          <div>
            <p>👦🏻 Front-end developer junior with a strong passion for everything related to the technological world</p>
            <p>😳 I am curious guy and I never get tired to think of new things to create!</p>
            <p>🎓 I graduated in Digital Communication at the University of Milan</p>
            <p>📸 Photography is my biggest hobby</p>
          </div>
        </div>
        <div class="slide" data-anchor="skills" id="skills">
          <SkillsSection/>
        </div>
        <div class="slide" data-anchor="hobby">
          <h3>🚧 Under costruction! 😥</h3>
        </div>
      </div>
      <div class="section" id="section3">
        <Contacts/>
      </div>
      <div class="section fp-auto-height" id="section4">
        <Footer/>
      </div>
    </full-page>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import HomePage from "./components/HomePage.vue";
import MainTitle from "./components/MainTitle.vue";
import HamburgerMenu from "./components/minorComponents/HamburgerMenu.vue";
import MainMenu from "./components/minorComponents/MainMenu.vue";
import SkillsSection from "./components/SkillsSection.vue";
import Footer from "./components/Footer.vue";
import Contacts from "./components/Contacts.vue";

export default {
  name: "app",
  data() {
    return {
      options: {
        afterLoad: this.afterLoad,
        menu: "#menu",
        navigation: true,
        anchors: ["hi", "aboutme", "contacts", "#thanks"],
        navigationPosition: "right",
        navigationTooltips: ["&#128075;", "&#9757;", "&#128222;", "&#128640;"],
        showActiveTooltip: false,
        sectionSelector: ".section",
        slideSelector: ".slide",
        loopHorizontal: true,
        slidesNavigation: true,
        controlArrows: false,
        slidesNavPosition: "bottom"
        /* sectionsColor: [
          "#FFFFFF",
          "#FFFFFF",
          "#0798ec",
          "#EE1A59",
          "#fec401",
          "#1bcee6",
          "#2c3e4f",
          "#ba5be9",
          "#b4b8ab"
        ] */
      }
    };
  },
  components: {
    HelloWorld,
    HomePage,
    MainTitle,
    MainMenu,
    HamburgerMenu,
    SkillsSection,
    Footer,
    Contacts
  }
};
</script>

<style>
:root {
  --primary-color: #302ae6;
  --secondary-color: #536390;
  --font-color: #2c3e50;
  --bg-color: #fff;
  --heading-color: #292922;
  --email-color: #253443;
  --footer-bg: #e4e4e4;
}

[data-theme="dark"] {
  --primary-color: #060607;
  --secondary-color: #818cab;
  --font-color: #e1e1ff;
  --bg-color: #161625;
  --heading-color: #818cab;
  --email-color: #f6f8fa;
  --footer-bg: #49497b;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin: 0;
  background-color: var(--bg-color);
  color: var(--font-color);
}

.logo {
  position: fixed;
  top: 20px;
  left: 20px;
  background-color: var(--font-color);
  color: var(--bg-color);
  font-weight: 700;
  z-index: 99;
  font-size: 1em;
  -webkit-font-smoothing: antialiased;
  -moz-font-smoothing: antialiased;
  text-decoration: none;
  padding: 10px 9px;
  border-radius: 50%;
}

@media screen and (max-width: 575px) {
  .fp-section {
    padding: 0px 40px;
  }
  .title--big {
    font-size: 2.3rem;
  }
  #logo {
    display: none;
  }
}

#fp-nav {
  z-index: 0;
}

@media print {
  #section3,
  .fp-slide {
    width: 50% !important;
    float: left;
  }
  #section4 {
    display: none !important;
  }
}

#fp-nav ul li a span,
.fp-slidesNav ul li a span {
  background: var(--font-color);
}

#section4 {
  background: var(--footer-bg);
}
</style>

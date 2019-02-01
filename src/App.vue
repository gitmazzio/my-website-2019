<template>
  <div id="app">
    <span id="logo" class="logo">MM</span>
    <ul id="menu">
      <li data-menuanchor="hi" class="active">
        <a href="#hi">&lt; Hi /&gt;</a>
      </li>
      <li data-menuanchor="aboutme">
        <a href="#aboutme">&lt;AboutMe /&gt;</a>
      </li>
      <li data-menuanchor="contacts">
        <a href="#contacts">&lt;Contacts /&gt;</a>
      </li>
      <li>
        <a
          href="https://twitter.com/teomazzio"
          target="_blank"
          rel="noopener"
          class="icon__social"
          v-b-tooltip.hover
          title="@teomazzio"
        >
          <i>
            <svg viewBox="0 0 512 512">
              <path
                d="M419.6 168.6c-11.7 5.2-24.2 8.7-37.4 10.2 13.4-8.1 23.8-20.8 28.6-36 -12.6 7.5-26.5 12.9-41.3 15.8 -11.9-12.6-28.8-20.6-47.5-20.6 -42 0-72.9 39.2-63.4 79.9 -54.1-2.7-102.1-28.6-134.2-68 -17 29.2-8.8 67.5 20.1 86.9 -10.7-0.3-20.7-3.3-29.5-8.1 -0.7 30.2 20.9 58.4 52.2 64.6 -9.2 2.5-19.2 3.1-29.4 1.1 8.3 25.9 32.3 44.7 60.8 45.2 -27.4 21.4-61.8 31-96.4 27 28.8 18.5 63 29.2 99.8 29.2 120.8 0 189.1-102.1 185-193.6C399.9 193.1 410.9 181.7 419.6 168.6z"
              ></path>
            </svg>
          </i>
        </a>
      </li>
      <li>
        <a
          href="https://www.instagram.com/milandreamin/"
          target="_blank"
          rel="noopener"
          class="icon__social"
          v-b-tooltip.hover
          title="@milandreamin"
        >
          <i>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              <path
                d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"
              ></path>
            </svg>
          </i>
        </a>
      </li>
    </ul>
    <HamburgerMenu/>
    <full-page :options="options" id="fullpage" ref="fullpage">
      <div class="section" id="section1">
        <HomePage/>
      </div>
      <div class="section" id="section2">
        <div class="slide" data-anchor="/me">
          <MainTitle msg="AboutMe"/>
        </div>
        <div class="slide" data-anchor="skills" id="skills">
          <SkillsSection/>
        </div>
        <div class="slide" data-anchor="hobby">Slide 3</div>
        <div class="slide" data-anchor="degree">Slide 4</div>
      </div>
      <div class="section" id="section3">
        <h3>Section 3</h3>
      </div>
      <div class="section fp-auto-height" id="section4">
        <footer class="pt-4 pb-4">
          <div class="thanks-section">
            <h5>thanks to:</h5>
            <p>
              Vue.js team: 
              <a target="_blank" href="https://github.com/vuejs/vue">
              <i>
            <svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
          </i> Vue.js framework</a> 
            <p>
              <a target="_blank" href="https://github.com/alvarotrigo/">alvarotrigo</a>: 
              <a target="_blank" href="https://github.com/alvarotrigo/fullpage.js"><i>
            <svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
          </i> fullpage.js library</a> 
            </p>
            <p>
              Cover pic: 
              <a target="_blank" href="https://www.instagram.com/_paulearl/">
              <i>
            <svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24">
              <path
                d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"
              ></path>
            </svg>
          </i> @_paulearl</a> 
            </p>
          </div>
          <span style="font-size: small">© 2019 Matteo Mazziotti Some Rights Reserved</span>
        </footer>
      </div>
    </full-page>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import HomePage from "./components/HomePage.vue";
import MainTitle from "./components/MainTitle.vue";
import HamburgerMenu from "./components/minorComponents/HamburgerMenu.vue";
import SkillsSection from "./components/SkillsSection.vue";

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
        slidesNavPosition: "bottom",
        sectionsColor: [
          "#41b883",
          "#ff5f45",
          "#0798ec",
          "#EE1A59",
          "#fec401",
          "#1bcee6",
          "#2c3e4f",
          "#ba5be9",
          "#b4b8ab"
        ]
      }
    };
  },
  components: {
    HelloWorld,
    HomePage,
    MainTitle,
    HamburgerMenu,
    SkillsSection
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}

.logo {
  position: fixed;
  top: 20px;
  left: 20px;
  color: #fff;
  font-weight: 700;
  z-index: 99;
  font-size: 1em;
  -webkit-font-smoothing: antialiased;
  -moz-font-smoothing: antialiased;
  text-decoration: none;
  background: #2c3e50;
  padding: 10px 7px;
  border-radius: 50%;
}

#menu {
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 70;
  -webkit-font-smoothing: antialiased;
  -moz-font-smoothing: antialiased;
  letter-spacing: 1px;
  font-size: 1.1em;
}

#menu a {
  color: #fff;
  padding: 0 1.1em 1.1em 1.1em;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.icon__social {
  fill: #fff;
}

@media only screen and (max-width: 600px) {
  #menu {
    display: none;
  }
}

@media screen and (max-width: 600px) {
  #logo {
    display: none;
  }
}

footer{
  font-size: x-small;
  color: #ffffff;
}
footer a, a:hover, a:active, a::after{
  text-decoration: none!important;
  color: #ffffff!important;
}

</style>

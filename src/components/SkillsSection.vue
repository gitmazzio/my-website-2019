<template>
  <div class="row ml-1 mr-1">
    <div class="col-sm-6 m-auto">
      <MainTitle msg="Skills"/>

      <b-button
        @click="addNewSkillToDOM"
        variant="light"
        class="sticky-bottom mt-2"
        :disabled="skillsIndex === otherSkills.length"
      >
        <span v-if="skillsIndex !== otherSkills.length">Add skill! &#128584;</span>
        <span v-else>No more skills &#128517;</span>
      </b-button>
      <p class="x-small mt-3">
        These skills come from LinkedIn!
        <br>I have not imagined them, I swear!
      </p>
    </div>

    <div class="col-sm-6 mt-2">
      <div id="containerSkills"></div>
      <div></div>
    </div>
  </div>
</template>

<script>
import MainTitle from "./MainTitle.vue";

export default {
  data() {
    return {
      emojis: [
        "✌",
        "😂",
        "😝",
        "😁",
        "😱",
        "👉",
        "🙌",
        "🍻",
        "🔥",
        "🌈",
        "☀",
        "🎈",
        "⚽",
        "🎾",
        "🏁",
        "🐻",
        "🐶",
        "🐬",
        "🐟",
        "🍀",
        "👀",
        "🚗",
        "🍎",
        "💝",
        "💙",
        "👌",
        "❤",
        "😍",
        "😉",
        "😓",
        "😳",
        "💪",
        "🍸",
        "🌟",
        "🎉",
        "🎶",
        "🏈",
        "⚾",
        "🏆",
        "👽",
        "💀",
        "🐵",
        "🐎",
        "💣",
        "👃",
        "👂",
        "👊",
        "💋",
        "😘",
        "😜",
        "😵",
        "🙏",
        "👋",
        "🚽",
        "💃",
        "💎",
        "🚀",
        "🌙",
        "🎁",
        "⛄",
        "🌊",
        "🏀",
        "💰",
        "👶",
        "🐰",
        "🔫",
        "🚲",
        "🍉",
        "💛",
        "💚"
      ],
      pageWidth: Math.max(
        document.documentElement.clientWidth,
        window.innerWidth || 0
      ),
      pageHeight: Math.max(
        document.documentElement.clientHeight,
        window.innerHeight || 0
      ),
      nextSkill: null,
      skillsIndex: 0,
      skills: [
        {
          name: "Web design",
          importance: 3
        },
        {
          name: "HTML5",
          importance: 3
        },
        {
          name: "CSS",
          importance: 3
        },
        {
          name: "Javascript",
          importance: 3
        },
        {
          name: "Vue.js",
          importance: 2
        },
        {
          name: "Java",
          importance: 2
        },
        {
          name: "Express.js",
          importance: 2
        },
        {
          name: "Photoshop",
          importance: 2
        },
        {
          name: "Illustrator",
          importance: 2
        },
        {
          name: "Git",
          importance: 2
        },
        {
          name: "SQL",
          importance: 2
        }
      ],
      priorityHigh: null,
      otherSkills: null
    };
  },
  created() {
    this.priorityHigh = this.skills.filter(elem => elem.importance === 3);
    this.otherSkills = this.skills.filter(x => !this.priorityHigh.includes(x));
  },
  mounted() {
    this.addPrioritySkills();
  },
  components: {
    MainTitle
  },
  methods: {
    addPrioritySkills() {
      // console.log(this.priorityHigh);
      this.priorityHigh.forEach(elem => {
        this.addSkill(elem.name, elem.competence, "skills__bigger");
      });
    },
    addSkill(skill, competence, skillClass) {
      var randomNumber = Math.floor(Math.random() * this.emojis.length);

      let elem = document.createElement("p");

      //elem.style.top = randomHeight + "px";
      //elem.style.marginLeft = randomWidth+ "px";
      //elem.classList.add("positioned__random");
      skillClass != null ? elem.classList.add(skillClass) : null;

      elem.innerHTML = this.emojis[randomNumber] + " " + skill;

      // console.log(mainDiv.childNodes);
      document.getElementById("containerSkills").appendChild(elem);
    },
    addNewSkillToDOM() {
      this.nextSkill = this.otherSkills[this.skillsIndex];
      this.addSkill(this.nextSkill.name, "skills__middle");
      this.skillsIndex++;
    }
  }
};
</script>

<style>
.positioned__random {
  position: absolute;
}
.skills__bigger {
  font-size: 1.3em;
  color: var(--font-color);
}
.skills__middle {
  font-size: 0.8em;
  color: var(--font-color);
}

@media screen and (max-width: 575px) {
  .skills__bigger {
    font-size: 1rem;
  }

  .skills__middle {
    font-size: 0.7rem;
  }
}

@media screen and (max-width: 320px) {
  #containerSkills p {
    margin-bottom: 0;
  }
}

.x-small {
  font-size: x-small;
}
</style>

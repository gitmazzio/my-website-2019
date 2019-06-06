<template>
  <div>
    <MainTitle msg="Skills"/>
    <b-button
      @click="addNewSkillToDOM"
      variant="secondary"
      class="sticky-bottom"
      :disabled="skillsIndex === otherSkills.length"
    >
      <span v-if="skillsIndex !== otherSkills.length">Add skill! &#128584;</span>
      <span v-else>No more skills &#128517;</span>
    </b-button>
  </div>
</template>

<script>
import MainTitle from "./MainTitle.vue";

export default {
  data() {
    return {
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
          name: "Java",
          importance: 2
        },
        {
          name: "Vue.js",
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
          name: "Java",
          importance: 3
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
      //console.log(this.priorityHigh);
      this.priorityHigh.forEach(elem => {
        this.addSkill(elem.name, "skills__bigger");
      });
    },
    addSkill(skill, skillClass) {
      var randomWidth =
        Math.floor(Math.random() * (this.pageWidth / 2)) + this.pageWidth / 4;
      var randomHeight =
        Math.floor(Math.random() * (this.pageHeight / 2)) + this.pageHeight / 4;
      var randomRoundWidth =
        Math.floor(Math.random() * (this.pageWidth / 6)) + this.pageWidth / 12;

      // let mainDiv = document.getElementById("skills");
      let elem = document.createElement("p");
      elem.style.top = randomHeight + "px";
      elem.style.marginLeft = randomWidth + "px";
      elem.style.width = randomRoundWidth + "px";
      elem.style.height = randomRoundWidth + "px";
      elem.classList.add("positioned__random");
      elem.classList.add("roundedSkill");
      skillClass != null ? elem.classList.add(skillClass) : null;
      elem.innerText = skill;
      // console.log(mainDiv.childNodes);
      document.getElementById("skills").childNodes[0].prepend(elem);
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
  font-size: 2em;
  color: var(--font-color);
}
.skills__middle {
  font-size: 1.5em;
  color: #ffffff;
}
.roundedSkill {
  background: rgba(0, 0, 0, 0.5);

  border-radius: 50%;
  color: #fff;
  line-height: 500px;
  text-align: center;
}

@media screen and (max-width: 575px) {
  .skills__bigger {
    font-size: 1.5rem;
  }

  .skills__middle {
    font-size: 0.7rem;
  }
}
</style>

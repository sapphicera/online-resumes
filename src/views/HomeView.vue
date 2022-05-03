<script>
import ExperienceEdu from "@/components/ExperienceEdu.vue";
import Capstone from "@/components/Capstone.vue";
import axios from "axios";

var TwitterWidgetsLoader = require('twitter-widgets');

export default {
  components: { ExperienceEdu, Capstone },
  data: function () {
    return {
      student: {},
      skillList: "",
    };
  },
  mounted() {
    TwitterWidgetsLoader.load();
  },
  created: function () {
    this.howStudent();
  },
  methods: {
    howStudent: function () {
      axios.get(`/students/1.json`).then(response => {
        console.log('getting student info', response.data)
        this.student = response.data;
      }).then(() => {
        this.skillString();
      })
    },
    skillString: function () {
      let skillz = this.student.skills;
      for (let id = 0; id < skillz.length - 1; id++) {
        this.skillList += `${skillz[id].skill}, `
      }
      this.skillList += `${skillz[skillz.length - 1].skill}`
    }
  },
};
</script>

<template>
  <h1>{{ this.student.first_name }} {{ this.student.last_name }}'s Resume</h1>
  <br /> <br />

  <div class="container">
    <div class="left-align">

      <div class="row">
        <div class="col-md-8">
          <h2>{{ student.first_name }} {{ student.last_name }}</h2>
        </div>
        <div class="col-md-4">
          <p class="float-end"><img class="size"
              src="https://images.unsplash.com/photo-1558021211-6d1403321394?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=426&q=80">
          </p>
        </div>
      </div>

      <div>
        <strong>{{ student.email }}</strong> |
        <strong>{{ student.phone_number }}</strong> |
        <strong>{{ student.personal_website }}</strong> |
        <strong>{{ student.linkedin_url }}</strong> |
        <strong>{{ student.twitter_handle }}</strong> |
        <strong>{{ student.github_url }}</strong>
      </div>

      <hr />

      <h2>Learn More About Me</h2>
      <p>{{ student.short_bio }}</p>

      <h2>Skills</h2>
      <p>{{ skillList }}</p>

      <h2>Education</h2>
      <div v-for="education in student.educations" v-bind:key="education.id">
        <ExperienceEdu :compuni="education.university_name" :jobdeg="education.degree" :start="education.start_date"
          :end="education.end_date" :details="education.details" />
      </div>

      <h2>Experience</h2>
      <div v-for="experience in student.experiences" v-bind:key="experience.id">
        <ExperienceEdu :compuni="experience.company_name" :jobdeg="experience.job_title" :start="experience.start_date"
          :end="experience.end_date" :details="experience.details" />
      </div>

      <h2>Capstone</h2>
      <div v-for="capstone in student.capstones" v-bind:key="capstone.id">
        <Capstone :name="capstone.name" :url="capstone.url" :details="capstone.description" />
        <div v-if="capstone.screenshot">
          <div class="ratio ratio-16x9">
            <div> <img v-bind:src="capstone.screenshot" class="img-fluid" alt="..."></div>
          </div>
        </div>
      </div>

    </div>
  </div>

  <!-- twitter widget -->
  <br /> <br /><br />
  <a class="twitter-timeline" data-width="400" data-height="400"
    href="https://twitter.com/TwitterDev?ref_src=twsrc%5Etfw">Tweets by TwitterDev</a>

</template>

<style>
.left-align {
  text-align: left;
}

.size {
  width: 200px;
  height: 200px;
}
</style>
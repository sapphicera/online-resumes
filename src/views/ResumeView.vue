<script>
import ExperienceEdu from "@/components/ExperienceEdu.vue";
import CapstoneShow from "@/components/CapstoneShow.vue";
import axios from "axios";

var TwitterWidgetsLoader = require('twitter-widgets');

export default {
  components: { ExperienceEdu, CapstoneShow },
  data: function () {
    return {
      student: {
        capstone: [],
      },
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
      axios.get(`/students/${this.$route.params.id}.json`).then(response => {
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
  <h1>My Resume</h1>
  <br />

  <button type="button" class="btn btn-primary btn-lg">Download Resume as PDF</button>
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
      <CapstoneShow :name="student.capstone.name" :url="student.capstone.url" :details="student.capstone.description" />

      <div v-if="student.capstone.screenshot">
        <div class="ratio ratio-16x9">
          <div> <img v-bind:src="student.capstone.screenshot" class="img-fluid" alt="..."></div>
        </div>
      </div>

    </div>
  </div>

  <!-- twitter widget -->
  <br /> <br /><br />
  <a class="twitter-timeline" data-width="400" data-height="400"
    v-bind:href="`https://twitter.com/${student.twitter_handle}`">Tweets {{ student.first_name }}</a>

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
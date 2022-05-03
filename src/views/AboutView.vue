<script>
var TwitterWidgetsLoader = require('twitter-widgets');
import axios from 'axios'
axios
export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      student: [],
      educations: [],
      skills: [],
      experiences: [],
      capstones: []
    };
  },
  mounted() {
    TwitterWidgetsLoader.load();
  },
  created: function () { },
  methods: {
    showStudent: function () {
      axios.get(`/students/${this.student.id}`).then(response => {
        console.log('getting student info', response.data)
        this.student = response.data
      })
    },
    // showEducations: function () {
    //   axios.get(`/educations/${this.student.educations.id}`).then(response => {
    //     console.log('getting education info', response.data)
    //     this.educations = response.data
    //   })
    // },
    // showExperiences: function () {
    //   axios.get(`/experiences/${this.student.experiences.id}`).then(response => {
    //     console.log('getting experience info', response.data)
    //     this.experiences = response.data
    //   })
    // },
    // showSkills: function () {
    //   axios.get(`/skills/${this.student.skills.id}`).then(response => {
    //     console.log('getting skill info', response.data)
    //     this.skills = response.data
    //   })
    // },
    // showCapstones: function () {
    //   axios.get(`/capstones/${this.student.capstones.id}`).then(response => {
    //     console.log('getting capstone info', response.data)
    //     this.capstones = response.data
    //   })
    // },
  },
};
</script>

<template>
  <a class="twitter-timeline" data-width="400" data-height="400"
    href="https://twitter.com/TwitterDev?ref_src=twsrc%5Etfw">Tweets by TwitterDev</a>
  <div class="home">
    <h1>{{ message }}</h1>
  </div>
</template>

<style>
</style>

<script>
import ExperienceEdu from "@/components/ExperienceEdu.vue";
import Capstone from "@/components/Capstone.vue";

var TwitterWidgetsLoader = require('twitter-widgets');

export default {
  components: { ExperienceEdu, Capstone },
  data: function () {
    return {
      message: "Student Resume",
      hasImage: true,
    };
  },
  mounted() {
    TwitterWidgetsLoader.load();
  },
  created: function () { },
  methods: {},
};
</script>

<template>
  <h1>{{ message }}</h1>

  <div class="container">
    <div class="left-align">

      <div class="row">
        <div class="col-md-8">
          <span id="label">
            <h2>Ben Jelinek</h2>
          </span>
        </div>

        <div class="col-md-4">
          <p class="float-end"><img class="size"
              src="https://images.unsplash.com/photo-1558021211-6d1403321394?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=426&q=80">
          </p>
        </div>
      </div>

      <b-container class="row">
        <b-row>
          <strong>
            <b-col>bjelinek42@gmail.com</b-col>
          </strong> |
          <strong>
            <b-col>319-521-1036</b-col>
          </strong> |
          <strong>
            <b-col>bjelinek42.github.io</b-col>
          </strong> |
          <strong>
            <b-col>linkedin.com/in/bjelinek/</b-col>
          </strong> |
          <strong>
            <b-col>@twitterhandle</b-col>
          </strong> |
          <strong>
            <b-col>bengithub.com</b-col>
          </strong>
        </b-row>
      </b-container>
      <hr />

      <h2>Full-Stack Software Developer</h2>
      <p>As a web developer and former Chiropractor, I use many of the same skills in engineering that I developed as a
        physician. My strengths in communication, collaborating with other specialties to achieve a common goal, and
        creative problem solving are now coupled with technical skills such as Ruby, Rails, PostgreSQL, and many
        frontend languages. I am a full believer of having a growth mindset, diligence, and a sense of humor in the face
        of adversity. I flourish when I’m learning new things, troubleshooting, and helping others grow.</p>
      <h2>Skills</h2>
      <p>Ruby, Rails, Vue.js, JavaScript, HTML, CSS, PostgreSQL, Git, GitHub, APIs, Pair-Programming, Testing,
        Object-Oriented Programming, Bootstrap</p>

      <h2>Education</h2>
      <ExperienceEdu compuni="Actualize" jobdeg="Certificate in Full Stack Web Development" start="Jan" end="May 2022"
        details="Capstone Project grubLuv: personally building a full-stack web application in which users can collaborate on
        where to eat in a group, setting parameters and selecting their preferred destination, outputting a single
        choice
        based on their responses. Built in Ruby on Rails and Vue.js with Google Places API." />

      <h2>Experience</h2>
      <ExperienceEdu compuni="Colorado Accident and Injury" jobdeg="Chiropractic Physician " start="Oct 2019"
        end="Feb 2022" details="Collaborated with multidisciplinary physicians including medical doctors, pain management, physical therapist,
and psychologists to coordinate patient care following injuries in motor vehicle accidents" />

      <h2>Capstone</h2>
      <Capstone name="PROJECT NAME" url="this is a url" details="details" />
      <div v-if="hasImage">
        <div class="ratio ratio-16x9">
          <div> <img src="https://gamelust.com/wp-content/uploads/2019/02/Apex-Legends-Screenshot-10-1920x1080.jpg"
              class="img-fluid" alt="..."></div>
        </div>
      </div>

    </div>
  </div>

  <!-- twitter widget -->
  <br />
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

.align-items-end {
  vertical-align: bottom;
}

.studentimg {
  vertical-align: baseline;
}

.label {
  display: inline-block;
}
</style>
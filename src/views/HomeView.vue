<script>
export default {
  data: function () {
    return {
      message: "Student Resume",
    };
  },
  created: function () { },
  methods: {},
};
</script>

<template>
  <div class="container">
    <h1>{{ message }}</h1>
    <div class="left-align">
      <!-- <div class="col-md-12">
        <h2>Ben Jelinek</h2>
        <p class="float-end"><img style='float:left;width:200px;height:200px; margin-right:10px;'
            src="https://images.unsplash.com/photo-1558021211-6d1403321394?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=426&q=80g" />
        </p>
      </div> -->
      <b-container class="row">
        <b-row>
          <b-col class="align-items-end">
            <p class="float-end"><img class="size"
                src="https://images.unsplash.com/photo-1558021211-6d1403321394?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=426&q=80">
            </p>
          </b-col>
          <strong>
            <b-col class="align-text-bottom">
              <h2>Ben Jelinek</h2>
            </b-col>
          </strong>
        </b-row>
      </b-container>

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
          </strong> |
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
    </div>
  </div>

</template>

<style>
.left-align {
  text-align: left;
}

.size {
  width: 200px;
  height: 200px
}

.align-items-end {
  vertical-align: bottom;
}
</style>

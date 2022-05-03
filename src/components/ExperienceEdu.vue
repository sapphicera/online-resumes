<script>
export default {
  name: "ExperienceEdu",
  props: ['compuni', 'jobdeg', 'start', 'end', 'details']
}
</script>

<template>
  <div class="row">
    <div class="col-md-8"><strong>{{ compuni }} || {{ jobdeg }}</strong></div>
    <div class="col-6 col-md-4">
      <p class="float-end">{{ start }} - {{ end }}</p>
    </div>
  </div>
  <li> {{ details }}</li>
  <br />
</template>

<style>
</style>
<script>
export default {
  name: "CapstoneShow",
  props: ['name', 'url', 'details']
}
</script>

<template>
  <div class="row">
    <div class="col-md-8"><strong>{{ name }}</strong></div>
    <div class="col-6 col-md-4">
      <p class="float-end">{{ url }}</p>
    </div>
  </div>
  <li>{{ details }}</li>
  <br />
</template>

<style>
</style>
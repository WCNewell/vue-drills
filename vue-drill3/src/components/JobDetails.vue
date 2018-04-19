<template>
  <div>
    <section id='job-details'>
      <h2>Job Details</h2>
      <h4>{{ jobDetails.title }}</h4>
      <p>{{ jobDetails.description }}</p>
    </section>
  </div>
</template>

<script>
export default {
  name: 'JobDetails',
  props: ['jobDetails']
}
</script>

<style scoped>

</style>
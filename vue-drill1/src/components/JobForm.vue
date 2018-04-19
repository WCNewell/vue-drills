<template>
  <div id='job-form'>
    <h3 id='job-form-title'>Add a Job</h3>
    <form @submit.prevent="submitForm">
      <label for="title">Title</label>
      <input type="text" name="title" v-model="job.title">
      <label for="pay">Compensation</label>
      <input type="text" name="pay" v-model="job.pay">
      <label for="description">Description</label>
      <textarea name="description" rows="8" cols="40" v-model="job.description"></textarea>
      <input type="submit" name="submit" value="Submit" />
    </form>
  </div>
</template>
<script>
export default {
  name: 'JobForm',
  props: {
    addJob: {
      type: Function,
      required: true
    }
  },
  data () {
    return {
      job: {
        title: '',
        pay: '',
        description: '',
        interested: []
      }
    }
  },
  methods: {
    submitForm () {
      this.addJob(this.job)
      this.job = {
        title: '',
        pay: '',
        description: '',
        interested: []
      }
    }
  }
}
</script>

<style scoped>
#job-form {
  grid-column: 4/5;
}
#job-form-title {
  display: flex;
}
form {
  display: flex;
  flex-flow: column;
  justify-content: space-around;
}
</style>

<template>
  <div>
    <h2>Job Listings</h2>
    <ul v-for='job in jobs' :key='job.title'>
      <li class='job-cards'>
        <h4>{{ job.title }}</h4>
        <small>{{ job.pay }}</small>
        <p>{{ job.description }}</p>
        <small>{{ job.interested.length }} dinos are interested in this job</small>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'JobList',
  props: {
    jobs: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
  .job-cards {
    display: flex;
    flex-flow: column;
    border-radius: 6px;
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
    margin-bottom: 10px;
    padding: 10px;
    align-items: flex-start;
  }
  h2 {
    margin: 0;
    color: #61CCB1;
  }
  ul {
    list-style: none;
  }
  h4 {
    margin: 0;
  }
  small {
    color: black;
    font-size: .5rem;
    margin-left: 10px;
  }
  p { 
    font-size: .8rem;
  }
</style>

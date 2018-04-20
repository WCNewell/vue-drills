<template>
  <div id='app'>
    <PageTitle></PageTitle>
    <main>
      <JobList id='job-listings' :jobs='jobs'></JobList>
      <JobForm :addJob='addJob'/>
    </main>
    <PageFooter></PageFooter>
</div> 
</template>

<script>
import PageTitle from '@/components/PageTitle'
import JobList from '@/components/JobList'
import JobForm from '@/components/JobForm'
import PageFooter from '@/components/PageFooter'

export default {
  name: 'App',
  components: {
    PageTitle,
    JobList,
    JobForm,
    PageFooter
  },
  data () {
    return {
      jobs: []
    }
  },
  mounted () {
    const url = '../../static/listings.json'
    fetch(url)
      .then(response => response.json())
      .then(result => {
        this.jobs = result
      })
  },
  methods: {
    addJob (job) {
      this.jobs.splice(0, 0, job)
    }
  }
}
</script>

<style>
html {
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}
main {
  grid-row: 2/3;
  display: grid;
  grid-template-columns: 5% 42.5% 5% 42.5% 5%;
}
#job-listings {
  grid-column: 2/3;
}
</style>

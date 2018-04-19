<template>
  <div id="app">
    <Header />
    <main>
      <JobDetails :jobDetails="jobApi"/>
      <InputForm :getText="getText"/>
      <button id='preview-toggle' @click="togglePreview = !togglePreview">Show Preview</button>
      <Preview :text='appText' :class='{hidden : togglePreview}'/>
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import JobDetails from './components/JobDetails.vue'
import InputForm from './components/InputForm.vue'
import Preview from './components/Preview.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  components: {
    Header,
    JobDetails,
    InputForm,
    Preview,
    Footer
  },
  data () {
    return {
    togglePreview: true,
    appText: '',
    jobApi: {}
    }
  },
  created () {
    const url = './listing.json'
    fetch(url)
    .then(response => response.json())
    .then(result => {
      this.jobApi = result
    })
  },
  methods: {
    getText(text) {
      this.appText = text
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
  color: #1B997A;
  margin-top: 60px;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}
main {
  grid-row: 2/3;
  width: 70%;
  margin: 0 auto;
  padding: 10px;
}
/* body {
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
} */
small {
  color: black;
  font-size: .5rem;
  margin-left: 10px;
}
/* a {
  color: #C261CC;
  text-decoration: none;
} */
.hidden {
  display: none;
}
</style>

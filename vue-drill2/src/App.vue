<template>
  <div id="app">
    <TheHeader></TheHeader>
    <main>
      <h1>Profiles</h1>
        <ul id='profiles'>
          <ProfileCards v-for="(dino, index) in dinos" :key='index' :dino='dino'></ProfileCards>
        </ul>
    </main>
    <TheFooter></TheFooter>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import ProfileCards from './components/ProfileCards.vue'
import SkillsLists from './components/SkillsLists.vue'
import TheFooter from './components/TheFooter.vue'

export default {
  name: 'app',
  components: {
    TheHeader,
    ProfileCards,
    SkillsLists,
    TheFooter
  },
  data () {
    return {
      dinos: []
    }
  },
  mounted () {
    const url = './dinosaurs.json'
    fetch(url)
    .then(response => response.json())
    .then(result => {
      this.dinos = result
    })
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
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}
h1 {
  margin-left: 100px;
}
</style>

<template>
  <li class='profile-cards'>
    <header class='profile-header' @click='skillsToggle = !skillsToggle'>
      <img :src='dino.image' />
      <h2>{{ dino.name }}</h2>
    </header>
    <section :class='{ hidden : skillsToggle }'>
      <h4>Skills</h4>
      <SkillsLists :skills='dino.skills'></SkillsLists>
    </section>
  </li>
</template>

<script>
import SkillsLists from './SkillsLists'

export default {
  name: 'ProfileCards',
  components: {
    SkillsLists
  },
  props: {
      dino: {
          type: Object,
          required: true
      }
  },
  data () {
    return {
      skillsToggle: true
    }
  }
}
</script>

<style scoped>
.profile-cards {
    border-radius: 6px;
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
    padding: 10px;
  }
  .profile-header {
    display: flex;
    flex-flow: row nowrap;
  }
  .profile-header img {
    width: 100px;
    height: 100px;
    border: 1px solid darkgrey;
    margin: 0 10px 0 10px;
  }
  .hidden {
    display: none;
  }
</style>
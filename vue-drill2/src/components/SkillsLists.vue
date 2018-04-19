<template>
  <ul class='skills-list'>
    <li v-for='(skill, index) in skills' :key='index'>{{ skill }}</li> 
  </ul>
</template>

<script>
export default {
  name: 'SkillsList',
  props: {
    skills: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
  .skills-list {
    list-style: none;
  }
</style>
<template>
  <div>
    <form>
      <label>Apply Here: </label>
      <textarea id='application-text' rows='8' cols='100' v-model='appText'></textarea>
      <input id='submit' type='submit' value='Submit' @click.prevent='submitApp' />
    </form>
    <p id='message'>{{ message }}</p>
  </div>
</template>

<script>
export default {
  name: 'InputForm',
  props: {
    getText: {
      type: Function,
      required: true
    }
  },
  data () {
    return {
      appText: '',
      message: ''
    }
  },
  watch: {
    appText (newText) {
      this.getText(newText)
    }
  },
  methods: {
    submitApp() {
      this.message = 'Your application was submitted!'
    }
  }
}
</script>

<style scoped>
form {
  display: block;
}
</style>

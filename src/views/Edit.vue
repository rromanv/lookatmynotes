<template>
  <Form edit :note="note" />
</template>

<script>
import Form from '../components/Form'

export default {
  name: 'Edit',
  data() {
    return {
      note: {}
    }
  },
  components: {
    Form
  },
  methods: {
    goToHome() {
      this.$router.push('/')
    }
  },
  mounted() {
    if (this.$route.query?.id) {
      const note = this.$store.getters.getNote(this.$route.query.id)
      if (note) {
        this.note = note
      } else {
        this.goToHome()
      }
    } else {
      this.goToHome()
    }
  }
}
</script>

<style lang="scss" scoped></style>

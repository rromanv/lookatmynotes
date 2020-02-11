<template>
  <div class="flex flex-wrap justify-center pt-8">
    <Card v-for="note in notes" :key="note.id" :note="note" />
    <router-link
      class=" bg-white h-12 w-full m-4 rounded-lg shadow hover:shadow-lg flex justify-center items-center hover:bg-gray-100"
      to="/add"
      ><div
        class="bg-white w-8 h-8 flex justify-center items-center rounded-full border-dashed border text-black"
      >
        <span class="text-gray-600 ">+</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import Card from '../components/Card'

export default {
  name: 'App',
  components: {
    Card
  },
  computed: {
    notes() {
      return this.$store.getters.getNotes
    }
  }
}
</script>

<style lang="scss" scoped></style>

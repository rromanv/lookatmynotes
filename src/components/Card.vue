<template>
  <div class="bg-white w-1/5 mx-4 mb-4 rounded-lg shadow p-4 text-black">
    <h1 class="text-2xl text-blue-900">{{ note.title }}</h1>
    <p>{{ note.content }}</p>
    <div class="flex justify-end text-xs">
      <button class="text-green-500 pr-2" @click="edit(note.id)">Edit</button>
      <button class="text-red-500" @click="remove(note.id)">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    note: {
      type: Object,
      default: () => ({
        id: 0,
        title: '',
        content: ''
      })
    }
  },
  methods: {
    remove(id) {
      this.$store.dispatch('removeNote', id)
    },
    edit(id) {
      this.$router.push({ path: '/edit', query: { id } })
    }
  }
}
</script>

<style lang="scss" scoped></style>

<template>
  <div class="bg-gray-700 min-h-screen text-white">
    <NavBar />
    <router-view />
  </div>
</template>

<script>
import NavBar from './components/NavBar'

export default {
  name: 'App',
  components: {
    NavBar
  }
}
</script>

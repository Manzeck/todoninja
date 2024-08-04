<template>
  <v-app class="bg-grey">
    <AppNavbar />
    <v-main class="mx-4 mb-4s">
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
import AppNavbar from './components/AppNavbar.vue'

export default {
  name: 'App',
  components: { AppNavbar },
  setup() {
    
  },
}
</script>
<style>
.bg-purple{
  background: #3a028f;
}
</style>

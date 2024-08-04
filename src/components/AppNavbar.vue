<template>
  <nav>
    <v-toolbar>
      <v-app-bar-nav-icon variant="text" class="text-grey" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-grey text-uppercase">
        <span class="font-weight-light">Todo</span>
        <span>Ninja</span>
      </v-toolbar-title>
      

      <v-menu>
        <template v-slot:activator="{ props }" >
          <v-btn  variant="flat" color="grey" v-bind="props" prepend-icon="mdi-chevron-down" class="mr-5">
            <span>Menu</span>
          </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="link in links" :key="link.text" rounter :to="link.route">
            <v-list-title>{{ link.text }}</v-list-title>
          </v-list-item>
        </v-list>
      </v-menu>
      
      
      <v-btn variant="flat" color="grey" append-icon="mdi-exit-to-app">
        <span>Sign Out</span>
      </v-btn>
    </v-toolbar>

    <v-navigation-drawer v-model="drawer" class="bg-primary" temporary>
      <v-col class="text-center mt-5">
        <v-avatar size="100">
          <v-img src="IMG_3289.PNG"></v-img>
        </v-avatar>
        <p class="text-white text-subtitle-1 mt-2">Luffy</p>
      </v-col>
      <v-col class="mt-4 mb-3 text-center">
          <AppPopup/>
        </v-col>
      <v-list>
        <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
          <v-icon :icon="link.icon" class="pr-2"></v-icon>
          <v-list-item-content>
            <v-list-title>{{ link.text }}</v-list-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
import AppPopup from './AppPopup.vue';

export default {
  components: {AppPopup},
  data: () => {
    return {
      drawer: false,
      links: [
        { icon: 'mdi-view-dashboard', text: 'Dashboard', route: '/' },
        { icon: 'mdi-folder', text: 'My Projects', route: '/projects' },
        { icon: 'mdi-account', text: 'Team', route: '/team' },
      ]
    }
  }

}
</script>

<style>


</style>

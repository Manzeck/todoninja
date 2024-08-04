<template>
  <div class="team">
    <h1 class="text-subtitle-1 text-grey">Team</h1>

    <v-container class="my-5">
      
      <v-row>
        <v-col xs="12" sm="6" md="4" lg="3" v-for="person in team" :key="person.name">
          <v-card variant="flat" class="text-center ma-3">
            <v-responsive class="pt-4">
              <v-avatar size="100" class="bg-grey">
                <v-img :src="person.avatar"></v-img>
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="text-grey">{{ person.role }}</div>
            </v-card-text>
            <v-card-action>
              <v-btn variant="flat" class="text-grey float-left" prepend-icon= "mdi-message">Message</v-btn>
            </v-card-action>
          </v-card>
        </v-col>
      </v-row>

    </v-container>
  </div>

</template>

<script>

// Components

export default ({
  data() {
    return {
      team: [
        {name:'Eren', role:'Web Developer', avatar: '/IMG_5672.jpg'},
        {name:'Yuta', role:'Graphic Designer', avatar: '/IMG_6242.jpg'},
        {name:'Naruto', role:'UI/UX', avatar: '/IMG_6442.JPG'},
        {name:'Luffy', role:'Social Media Maverick', avatar: '/IMG_3289.PNG'},
        {name:'Goku', role:'Sales Guru', avatar: '/IMG_8176.JPG'},
      ]
    }
  }

});
</script>

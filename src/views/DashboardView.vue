<template>
  <div class="dasboard">
    <h1 class="text-subtitle-1 text-grey">Dashboard</h1>

    <v-container class="my-5">
      <v-row class="mb-3">
        <v-btn v-tooltip:top="'Sort Projects By Project Name'" prepend-icon= "mdi-folder" variant="flat" class="bg-grey" @click="sortBy('title')">
          <span class="text-subtitle-2">By Project Name</span>
        </v-btn>
        <v-btn v-tooltip:top="'Sort Projects By Person'" prepend-icon= "mdi-account" variant="flat" class="bg-grey" @click="sortBy('person')">
          <span class="text-subtitle-2">By Person</span>
        </v-btn>
      </v-row>

      <v-card variant="flat" class="pa-3" v-for="project in projects" :key="project.title">
        <v-row :class="`pa-3 project ${project.status}`">
          <v-col sm="12" md="6">
            <div class="text-subtitle-1 text-grey">Project Title</div>
            <div>{{ project.title }}</div>
          </v-col>
          <v-col xs="6" sm="4" md="2">
            <div class="text-subtitle-1 text-grey">Person</div>
            <div>{{ project.person }}</div>
          </v-col>
          <v-col xs="6" sm="4" md="2">
            <div class="text-subtitle-1 text-grey">Due by</div>
            <div>{{ project.due }}</div>
          </v-col>
          <v-col xs="2" sm="4" md="2">
            <div class="float-right">
              <v-chip size="small" :class="`${project.status} text-white text-subtitle-2 my-2`">{{ project.status }}</v-chip>
            </div>
          </v-col>
        </v-row>
        <v-divider></v-divider>
      </v-card>
    </v-container>
  </div>

</template>

<script>

// Components

export default ({
  data() {
    return{
      projects: [
        {title: 'Design a new website', person: 'Eren', due:'30th July 2024', status:'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati culpa ipsa error impedit modi dignissimos, rem optio laboriosam vel ducimus! Ad sint animi impedit quibusdam, cum alias molestias corrupti iure!'},
        {title: 'Code up a homepage', person: 'Yuta', due:'31th July 2024', status:'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati culpa ipsa error impedit modi dignissimos, rem optio laboriosam vel ducimus! Ad sint animi impedit quibusdam, cum alias molestias corrupti iure!'},
        {title: 'Design video thumbnails', person: 'Naruto', due:'1st August 2024', status:'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati culpa ipsa error impedit modi dignissimos, rem optio laboriosam vel ducimus! Ad sint animi impedit quibusdam, cum alias molestias corrupti iure!'},
        {title: 'Create a community forum', person: 'Luffy', due:'12 August 2024', status:'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati culpa ipsa error impedit modi dignissimos, rem optio laboriosam vel ducimus! Ad sint animi impedit quibusdam, cum alias molestias corrupti iure!'},
        {title: 'Web Gurus', person: 'Goku', due:'12 August 2024', status:'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati culpa ipsa error impedit modi dignissimos, rem optio laboriosam vel ducimus! Ad sint animi impedit quibusdam, cum alias molestias corrupti iure!'}
      ]
    }
  },
  methods: {
    sortBy(prop){
      this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
    }
  }

});
</script>

<style>
.project.complete {
  border-left: 4px solid #3cd1c2;
}
.project.ongoing {
  border-left: 4px solid orange;
}
.project.overdue {
  border-left: 4px solid tomato;
}
.v-chip.complete{
  background: #3cd1c2;
}
.v-chip.ongoing{
  background: orange
}
.v-chip.overdue{
  background: tomato
}
</style>

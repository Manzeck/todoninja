<template>
  <div class="project">
    <h1 class="text-subtitle-1 text-grey">Project</h1>

    <v-container class="my-5">
      <v-expansion-panels v-for="project in myProjects" :key="project.title">
        <v-expansion-panel>
          <v-expansion-panel-title>{{ project.title }}</v-expansion-panel-title>
          <v-expansion-panel-text class="px-4 text-grey">
            <div class="font-weight-bold">Due by xx.xx.xxxx</div>
            <div>{{ project.content }}</div>
          </v-expansion-panel-text>
        </v-expansion-panel>
      </v-expansion-panels>
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
        {title: 'Create a community forum.. again', person: 'Luffy', due:'12 August 2024', status:'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati culpa ipsa error impedit modi dignissimos, rem optio laboriosam vel ducimus! Ad sint animi impedit quibusdam, cum alias molestias corrupti iure!'},
        {title: 'Web Guru', person: 'Goku', due:'12 August 2024', status:'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati culpa ipsa error impedit modi dignissimos, rem optio laboriosam vel ducimus! Ad sint animi impedit quibusdam, cum alias molestias corrupti iure!'}
      ]
    }
  },
  computed: {
    myProjects(){
      return this.projects.filter(project => {
        return project.person === 'Luffy'
      })
    }
  }
});
</script>

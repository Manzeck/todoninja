<template>
  <v-dialog max-width="600">
    <template v-slot:activator="{ props }">
        <v-btn variant="flat" class="bg-success" v-bind="props">Add New Project</v-btn>
    </template>
    <v-card title="Add A New Project">
        <v-card-text>
            <v-form class="px-3">
                <v-text-field label="Title" v-model="title" prepend-icon="mdi-folder"></v-text-field>
                <v-textarea label="Information" v-model="content" prepend-icon="mdi-pencil"></v-textarea>

                <v-menu>
                    <template v-slot:activator="{ props }">
                        <v-text-field :value="due" label="Due Date"  v-bind="props" prepend-icon="mdi-calender-range"></v-text-field>
                    </template>
                    <v-date-picker v-model="due"></v-date-picker>
                </v-menu>

                <v-btn variant="flat" class="bg-success mx-0 mt-3" @click="submit">Add Project</v-btn>
            </v-form>
        </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
    data() {
        return {
            title: '',
            content: '',
            due: null
        }
    },
    methods: {
        submit() {
            console.log(this.title, this.content)
        }
    }
}
</script>

<style>

</style>
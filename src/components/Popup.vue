<template>
    <v-dialog
        max-width="600"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Add Project</v-btn>
        </template>
        <template>
          <v-card>
            <v-card-title>
                <h2>Add a New Project</h2>
            </v-card-title>
            <v-card-text>
                <v-form class="px-3">
                    <v-text-field v-model="title" label="title" prepend-icon="folder"></v-text-field>
                    <v-textarea v-model="content" label="Information" prepend-icon="edit"></v-textarea>
                        <!-- date  -->
                            <v-menu max-width="290">
                                <template v-slot:activator="{ on }">
                                    <v-text-field :value="formattedDate" label="Due date" prepend-icon="mdi-calendar-range" v-on="on"></v-text-field>
                                </template>
                                <v-date-picker v-model="due"></v-date-picker>
                            </v-menu>
                        <!-- end date  -->
                    <v-spacer></v-spacer>
                    <v-btn flat @click="submit" class="success mx-0 mt-3">Add Project</v-btn>
                </v-form>
            </v-card-text>
            </v-card>
        </template>
      </v-dialog>
</template>

<script>
import format from 'date-fns/format';
import parseISO from 'date-fns/esm/fp/parseISO';
export default {
    data(){
        return{
            title: '',
            content: '',
            due: null,
            menu: false
        }
    },
    methods: {
        submit(){
            alert('hi there');
        }
    },
    computed: {
        formattedDate(){
            return this.due ? format(parseISO(this.due), 'do MMM yyyy') : ''
        }
    }
}
</script>

<style>

</style>
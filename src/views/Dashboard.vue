<template>
  <div class="dashboard">
    <h1 class="subheading white--text darken-5">Dashboard</h1>

    <v-container class="my-5">
      <v-row class="px-3 mb-3">
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-col cols="2" >
              <v-btn small depressed class="grey--text" @click.prevent="filterby('title')" v-bind="attrs"
          v-on="on">
              <v-icon left small> mdi-folder </v-icon>
              <span class="caption text-lowercase">By project name</span>
            </v-btn>
            </v-col>
          </template>
          <span>Sort Projects By Names</span>
        </v-tooltip>

        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-col cols="2" >
              <v-btn small depressed class="grey--text" @click.prevent="filterby('person')" v-bind="attrs"
          v-on="on">
              <v-icon left small> mdi-folder </v-icon>
              <span class="caption text-lowercase">By project person</span>
            </v-btn>
            </v-col>
          </template>
          <span>Sort Projects By person</span>
        </v-tooltip>
      </v-row >

      <v-card flat class="px-3 my-4" v-for="project in projects" :key="project.title">
        <v-row row wrap :class="`pa-3 project ${project.status}`">
          <v-col cols="12" md="6">
            <div class="caption grey--text">Project Title</div>
            <div>{{project.title}}</div>
          </v-col>
          <v-col xs="6" >
            <div class="caption grey--text">Person</div>
          <div>{{project.person}}</div>
          </v-col >
          <v-col xs="6">
            <div class="caption grey--text">Due Date</div>
            <div>{{project.due}}</div>
          </v-col>
          <v-col xs="6">
            <div class="right">
              <v-chip small :color="`${project.status}`" 
                            :class="`v-chip--active white--text caption my-2`">
                              {{project.status}}
                            </v-chip>
            </div>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </div>
</template>
<script>
export default {
  data(){
    return{
      projects: [
        { title: 'Design a new website', person: 'The Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Code up the homepage', person: 'Chun Li', due: '10th Jan 2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Design video thumbnails', person: 'Ryu', due: '20th Dec 2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Create a community forum', person: 'Gouken', due: '20th Oct 2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
      ]
    }
  },
  methods:{
    filterby(value){
      this.projects.sort((a,b) => a[value] < b[value] ? -1 : 1)
    }
  }
}
</script>
<style>
.project.complete{
  border-left: 4px solid #3CD1C2;
}
.project.ongoing{
  border-left: 4px solid orange
}
.project.overdue{
  border-left: 4px solid tomato;
}
.v-chip.ongoing {
    background: #fed330 ;
  }
  .v-chip.complete {
    background: #26de81;
  }
  .v-chip.overdue {
    background: #fc5c65;
  }
</style>
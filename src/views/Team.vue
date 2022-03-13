<template>
  <div class="team">
    <h1 class="subheading grey--text">Team</h1>

    <v-container class="my-5">
      <v-row wrap>
        <v-col lg="3" md="4" sm="6" cols="12" v-for="person in team" :key="person.name">
          <v-card flat class="text-center ma-3 pa-3">
            <v-responsive>
              <v-avatar size="100" class="grey lighten-2">
                <img :src="person.avatar">
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="sub-heading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn flat small color="white">
                <v-icon small left>message</v-icon>
                <span class="">Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    
  </div>
</template>
<script>
export default {
  data() {
    return {
      team: [
        { name: 'The Net Ninja', role: 'Web developer', avatar: '/avatar-1.png' },
        { name: 'Ryu', role: 'Graphic designer', avatar: '/avatar-2.png' },
        { name: 'Chun Li', role: 'Web developer', avatar: '/avatar-3.png' },
        { name: 'Gouken', role: 'Social media maverick', avatar: '/avatar-4.png' },
        { name: 'Yoshi', role: 'Sales guru', avatar: '/avatar-5.png'}
      ]
    }
  }
}
</script>

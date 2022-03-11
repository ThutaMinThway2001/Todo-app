<template>
  <v-app >
    <v-main class="grey">
      <Navbar />
      <router-view></router-view>
    </v-main>
    
  </v-app>
</template>

<script>

import Navbar from './components/Navbar'
export default {
  name: 'App',

  components: {
    Navbar,
  },

  data: () => ({
    //
  }),
};
</script>
<style>
  #app{
    background-color: lightgray;
  }
</style>
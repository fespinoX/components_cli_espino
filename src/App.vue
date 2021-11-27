<template>
  <v-app>
    <v-app-bar
      app
      color="yellow"
      dark
    >
      <div class="d-flex align-center">
        <h1>Boardgametor 2000</h1>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://ohno.com.ar"
        target="_blank"
        text
      >
        <span class="mr-2">OHNO!</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <MainPage/>
    </v-main>
  </v-app>
</template>

<script>
import MainPage from './components/MainPage';

export default {
  name: 'App',

  components: {
    MainPage,
  },

  data: () => ({
  }),
};
</script>

<style>
  
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@200;400;500;600;700&display=swap');
  * {
    font-family: 'Roboto Mono', monospace;
  }

</style>
<style lang="sass" scoped>

  .v-toolbar
    h1
      font-size: 1.2rem
      color: #000

    .v-btn
      background-color: #000
      color: yellow

</style>

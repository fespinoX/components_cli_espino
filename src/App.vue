<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <p>Boardgametor 2000</p>
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

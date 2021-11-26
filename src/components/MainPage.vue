<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.png')"
          class="my-3"
          contain
          height="100"
        />
      </v-col>

      <v-col cols="12" class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          {{ title }}
        </h1>
      </v-col>

      <v-col
        sm="6"
        offset-sm="3"
        md="4"
        offset-md="4"
      >
        
        <BgSelect 
          :options="tipos"
          v-model="tipoDeJuego"
          @change="updateTipo"
        />
      </v-col>

      <v-col>
        <p>{{tipoDeJuego}}</p>
        <BgGamesTable :css-class="'style-party'" />
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
  import BgSelect from './BgSelect';
  import BgGamesTable from './BgGamesTable';
  export default {
    name: 'MainPage',
    components: {
      BgSelect,
      BgGamesTable
    },
    data: () => ({
      title: 'Boardgametor 2000',
      tipoDeJuego: {
        type: '',
          text: ''
      },
      tipos: [
        {
          type: 'bgParty',
          text: 'Casual'
        },
        {
          type: 'bgMedio',
          text: 'Medio'
        },
        {
          type: 'bgPro',
          text: 'Pro'
        },
      ]
    }),
    methods: {
      updateTipo() {
        console.log("Month changed. Selected ID: ", this.tipoDeJuego.type);
      }
    }

  }
</script>

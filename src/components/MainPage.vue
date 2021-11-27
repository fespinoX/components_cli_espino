<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.png')"
          class="mt-8"
          contain
          height="100"
        />
      </v-col>

      <v-col cols="12">
        <h1 class="mb-3 main-title">
          {{ title }}
        </h1>
      </v-col>
    </v-row>
    <v-row class="text-center">
      <v-col
        sm="6"
        offset-sm="3"
        md="4"
        offset-md="4"
      >
        <div>
          <BgSelect 
            :options="juegos"
            :texto="'Seleccionar un tipo de juego'"
            v-model="tipoDeJuego"
          />
        </div>
      </v-col>
    </v-row>
    <v-row class="text-center">
      <v-col
        cols="12"
        v-if="tipoDeJuego.type != ''"
      >
        <div class="mb-4">
          <BgGamesTable 
            :css-class="tipoDeJuego.style"
            :tipo="tipoDeJuego"
          />
        </div>
      </v-col>
      <v-col
        xs="12"
        md="6"
        offset-md="3"
        v-else
      >
        <div>
          <Alert
            :border="'top'"
            :color="'yellow'"
            :textoAlerta="'Elegí un tipo de juego para ver las sugerencias'"
          />
        </div>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
  import BgSelect from './BgSelect';
  import BgGamesTable from './BgGamesTable';
  import Alert from './Alert.vue';
  export default {
    name: 'MainPage',
    components: {
      BgSelect,
      BgGamesTable,
      Alert
    },
    data: () => ({
      title: 'Boardgametor 2000',
      tipoDeJuego: {
        type: '',
          text: ''
      },
      juegos: [
        {
          type: 'bgParty',
          text: 'Casual',
          style: 'style-party',
          items: [
            {
              titulo: "Skull King",
              jugadoresMin: 2,
              jugadoresMax: 6,
              tiempoDeJuego: 30,
              foto: "https://cf.geekdo-images.com/jiL3MIGH_w3g6El3OHVVig__itemrep/img/tC74qzJUxzrgPZ54MBctKmx8pbg=/fit-in/246x300/filters:strip_icc()/pic6137456.png",
              descripcion: "En Skull King tus amigos y vos se convierten en piratas que apuestan para ver cuantas manos se van a llevar.",
              linkBgg: "https://boardgamegeek.com/boardgame/150145/skull-king",
            },
            {
              titulo: "The Game",
              jugadoresMin: 1,
              jugadoresMax: 5,
              tiempoDeJuego: 20,
              foto: "https://cf.geekdo-images.com/g4pn1ieUKfIhERl5Ym6joQ__itemrep/img/4fI4jFXRtKw-ItHIqpzp8tH7r1A=/fit-in/246x300/filters:strip_icc()/pic4203279.png",
              descripcion: "En The Game los jugadores juegan de manera cooperativa para quedarse sin cartas",
              linkBgg: "https://boardgamegeek.com/boardgame/173090/game",
            },
            {
              titulo: "That's Pretty Clever!",
              jugadoresMin: 1,
              jugadoresMax: 4,
              tiempoDeJuego: 30,
              foto: "https://cf.geekdo-images.com/3-unuy5JW1cC8C6EUBNiOA__itemrep/img/6BcSS0mLm9nJBIXTcz0HQ5SKJmI=/fit-in/246x300/filters:strip_icc()/pic4410877.jpg",
              descripcion: "En este juego 'roll & write', los jugadores se van turnando para tirar dados completando casillas y ganando puntos",
              linkBgg: "https://boardgamegeek.com/boardgame/244522/s-pretty-clever",
            },
            {   
              titulo: "Codenames",
              jugadoresMin: 2,
              jugadoresMax: 8,
              tiempoDeJuego: 15,
              foto: "https://cf.geekdo-images.com/F_KDEu0GjdClml8N7c8Imw__itemrep/img/e8zw8YQvQB8q8zfWkHQ48Ls920g=/fit-in/246x300/filters:strip_icc()/pic2582929.jpg",
              descripcion: "En Codenames los jugadores se dividen en dos equipos, asignado a un capitán que deberá guiar a su equipo a encontrar las palabras clave.",
              linkBgg: "https://boardgamegeek.com/boardgame/178900/codenames",
            }
          ]
        },
        {
          type: 'bgMedio',
          text: 'Medio',
          style: 'style-medio',
          items: [
            {
              titulo: "Azul",
              jugadoresMin: "2",
              jugadoresMax: "4",
              tiempoDeJuego: "45",
              foto: "https://cf.geekdo-images.com/tz19PfklMdAdjxV9WArraA__itemrep/img/EuG9Te3VDhT58DlEYeEVVunM5wY=/fit-in/246x300/filters:strip_icc()/pic3718275.jpg",
              descripcion: "En Azul cada jugador deberá ir seleccionando azulejos para completar su pared y así ganar puntos.",
              linkBgg: "https://boardgamegeek.com/boardgame/230802/azul",
            },
            {
              titulo: "Splendor",
              jugadoresMin: "2",
              jugadoresMax: "4",
              tiempoDeJuego: "30",
              foto: "https://cf.geekdo-images.com/rwOMxx4q5yuElIvo-1-OFw__itemrep/img/NaQx3XWoNAOMDGl4AXf4nxlhHo0=/fit-in/246x300/filters:strip_icc()/pic1904079.jpg",
              descripcion: "Cada uno de los jugadores compite por tener la joyería más prestigiosa del Renacimiento.",
              linkBgg: "https://boardgamegeek.com/boardgame/148228/splendor",
            },
            {
              titulo: "Dinosaur Island: Rawr 'n Write ",
              jugadoresMin: "1",
              jugadoresMax: "4",
              tiempoDeJuego: "45",
              foto: "https://cf.geekdo-images.com/xRP9jo5gfwhfFkgxQBgWTw__itemrep/img/1HA068DMDuzajRY0s_5PDc1BDhg=/fit-in/246x300/filters:strip_icc()/pic5622932.png",
              descripcion: "Cada jugador crea su propio parque jurásico y añade atracciones dibujándolas en un papel.",
              linkBgg: "https://boardgamegeek.com/boardgame/318009/dinosaur-island-rawr-n-write",
            },
            {   
              titulo: "Manhattan",
              jugadoresMin: "2",
              jugadoresMax: "4",
              tiempoDeJuego: "45",
              foto: "https://cf.geekdo-images.com/J38tww49pGTsp3bmgEekkA__itemrep/img/zEddKUhfmbz47gdfdSukuK53B44=/fit-in/246x300/filters:strip_icc()/pic3573055.png",
              descripcion: "Los jugadores van construyendo el paisaje de Manhattan, agregando edificios y subiendo la cantidad de pisos.",
              linkBgg: "https://boardgamegeek.com/boardgame/199/manhattan",
            }
          ]
        },
        {
          type: 'bgPro',
          text: 'Pro',
          style: 'style-pro',
          items: [
            {
              titulo: "Scythe",
              jugadoresMin: "1",
              jugadoresMax: "5",
              tiempoDeJuego: "115",
              foto: "https://cf.geekdo-images.com/7k_nOxpO9OGIjhLq2BUZdA__itemrep/img/RVh5N-_HcMziJ3M6Q1eLTlj8XIQ=/fit-in/246x300/filters:strip_icc()/pic3163924.jpg",
              descripcion: "Scythe nos plantea un mundo distópico en el cual luego de la primera guerra mundial los jugadores deberán cuidar su territorio e ir ampliándolo.",
              linkBgg: "https://boardgamegeek.com/boardgame/169786/scythe",
            },
            {
              titulo: "Roll Player",
              jugadoresMin: "1",
              jugadoresMax: "4",
              tiempoDeJuego: "90",
              foto: "https://cf.geekdo-images.com/enmQAOQl99U6wiQvZoL5GQ__itemrep/img/lEXrmts1iZPtAufiXjzxk6Ik9rg=/fit-in/246x300/filters:strip_icc()/pic2556921.jpg",
              descripcion: "Cada jugador deberá crear su propio personaje de rol, teniendo en cuenta diferentes stats para ganar más puntos",
              linkBgg: "https://boardgamegeek.com/boardgame/169426/roll-player",
            },
            {
              titulo: "Terraforming Mars",
              jugadoresMin: "1",
              jugadoresMax: "5",
              tiempoDeJuego: "120",
              foto: "https://cf.geekdo-images.com/wg9oOLcsKvDesSUdZQ4rxw__itemrep/img/IwUOQfhP5c0KcRJBY4X_hi3LpsY=/fit-in/246x300/filters:strip_icc()/pic3536616.jpg",
              descripcion: "Cada jugador representa una corporación que intenta conquistar Marte y hacerla habitable para los humanos.",
              linkBgg: "https://boardgamegeek.com/boardgame/167791/terraforming-mars",
            },
            {   
              titulo: "Viticulture",
              jugadoresMin: "2",
              jugadoresMax: "6",
              tiempoDeJuego: "90",
              foto: "https://cf.geekdo-images.com/WrnWFA1Sysm3-nQyBe1sUA__itemrep/img/c3Gex8FN8UwHHIChBqf1jUE-SWk=/fit-in/246x300/filters:strip_icc()/pic2619743.jpg",
              descripcion: "En Viticulture se crean viñedos y se cultivan uvas para hacer vino y venderlo al final de la temporada.",
              linkBgg: "https://boardgamegeek.com/boardgame/128621/viticulture",
            }
          ]
        },
      ],
    }),
    methods: {
    }

  }
</script>
<style lang="sass" scoped>

  .main-title
    font-weight: 900
    font-size: 3rem
    color: yellow

</style>
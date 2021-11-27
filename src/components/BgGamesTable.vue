<template>
  <table :class="['table-responsive', 'table-juegos', cssClass]">
    <thead class="juegos-head">
      <tr>
        <th class="table-title" scope="col">Foto</th>
        <th class="table-title" scope="col">Nombre</th>
        <th class="table-title" scope="col">Jugadores</th>
        <th class="table-title" scope="col">Tiempo</th>
        <th class="table-title" scope="col">Descripción</th>
      </tr>
    </thead>
    <tbody>
      <tr 
        class="juegos-row"
        v-for="(juego, i) in tipo.items" 
        :key="i" :titulo="juego.titulo" 
        :jugadoresMin="juego.jugadoresMin" 
        :jugadoresMax="juego.jugadoresMax"
      >
        <td>
          <img 
            :src="juego.foto"
            :alt="juego.titulo"
            class="juego-img"
          />
        </td>
        <td class="juego-titulo px-2">
          {{juego.titulo}}
        </td>
        <td>
          {{juego.jugadoresMin}}-{{juego.jugadoresMax}}
        </td>
        <td>
          {{juego.tiempoDeJuego}}'
        </td>
        <td class="px-2 py-4">
          <p class="juego-desc">{{juego.descripcion}}</p>
          <v-btn
            class="table-btn"
            target="_blank"
            :href="juego.linkBgg"
            color="yellow"
            small
          >
            Ver en BGG
          </v-btn>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
  export default {
    name: 'BgGamesTable',
    data: () => ({
    }),
    props: {
      tipo: {
        type: Object,
      },
      cssClass: {
        type: String,
        default: 'style-basic',
      }
    },
  }
</script>

<style lang="sass" scoped>

  .style-party
    tr
      background-color: #252525

  .style-medio
    tr
      background-color: #95638c

  .style-pro
    tr
      background-color: #8b5b5b            

  .table-title
    padding: 10px
    font-size: 1.1rem 

  .table-btn
    color: #000!important

  .juego-img
    max-width: 150px

  .juego-titulo
    font-weight: 500
    font-size: 1.1rem

  .juego-desc
    font-size: .8rem

</style>

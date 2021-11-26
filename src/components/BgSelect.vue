<template>
  <div>
    <v-select
      filled
      :items="options"
      item-text="text"
      item-value="type"
      label="Seleccionar un tipo de juego"
      dense
      return-object
      single-line
      @change="changeTipo"
      v-model="tipoDeJuego"
    ></v-select>
  </div>
</template>

<script>
  export default {
    name: 'BgSelect',
    props: {
      options: { 
        type: Array 
      }
    },
    data: function () {
      return {
        tipoDeJuego: {
          type: '',
          text: ''
        }
      }
    },
    methods: {
      changeTipo: function () {
        console.log("child changed: " + this.tipoDeJuego.type);

        this.$emit('input', this.tipoDeJuego);
      }
    }
  }
</script>

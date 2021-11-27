<template>
  <v-select
    filled
    :items="options"
    item-text="text"
    item-value="type"
    :label="texto"
    dense
    return-object
    single-line
    @change="changeTipo"
    v-model="tipoDeJuego"
  ></v-select>
</template>

<script>
  export default {
    name: 'BgSelect',
    props: {
      options: { 
        type: Array 
      },
      texto: {
        type: String,
        default: "Seleccioná una opción"
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
        this.$emit('input', this.tipoDeJuego);
      }
    }
  }
</script>

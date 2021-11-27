<template>
  <v-alert
    :border="border"
    :color="color"
    :type="type"
    elevation="2"
  >
    {{textoAlerta}}
  </v-alert>
</template>

<script>
  export default {
    name: 'Alert',
    props: {
      textoAlerta: {
        type: String,
        required: true
      },
      border: { 
        type: String,
        default: "top"
      },
      color: {
        type: String,
        default: "green"
      },
      type: {
        type: String,
      },
      texto: {
        type: String,
        default: "Seleccioná una opción"
      }
    },
    data: function () {
      return {
      }
    },
  }
</script>

<style lang="sass" scoped>

  .v-alert
    color: #000
    .v-alert__icon
      color: #000

</style>

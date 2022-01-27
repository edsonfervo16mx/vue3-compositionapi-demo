<template>
  <!--<h1>Detalle: {{ $route.params.nombre }}</h1>-->
  <h1>Detalle: {{ nombre }}</h1>
</template>

<script>
import { useRoute } from "vue-router";
export default {
  props: {
    nombre: {
      type: String,
      default: "",
    },
  },
  setup(props) {
    console.log(props.nombre);
    // Accediendo desde el params de route
    const nombreParams = useRoute();
    console.log(nombreParams.params.nombre);
  },
};
</script>

<style></style>

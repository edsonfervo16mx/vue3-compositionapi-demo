<template>
  <h1>Contador: {{ contador }}</h1>
  <btn :textoBoton="'Disminuir'" @accion="disminuir" />
  <btn :textoBoton="'Aumentar'" @accion="aumentar" />
</template>

<script>
import { useContador } from "../hooks/useContador";
import Btn from "../components/Btn.vue";
export default {
  components: { Btn },
  setup() {
    return { ...useContador() };
  },
};
</script>

<style></style>

<template>
  <h1>Monto: {{ signoPeso }}</h1>
</template>

<script>
import { computed } from "vue";
export default {
  props: {
    contador: {
      type: Number,
      default: 0,
    },
  },
  setup(props) {
    const signoPeso = computed(() => {
      return "$ " + props.contador;
    });

    return {
      signoPeso,
    };
  },
};
</script>

<style></style>

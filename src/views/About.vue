<template>
  <div class="about">
    <Titulo :contador="contador" />
    <h1 :style="{ color: color }">{{ contador }}</h1>
    <button @click="disminuir">-</button>
    <button @click="aumentar">+</button>
    <hr />
    <input type="text" v-model="texto" />
    <br />
    {{ texto }}
    <br />
    <br />
    <Btn :textoBoton="'Disminuir'" @accion="disminuir" />
    <Btn :textoBoton="'Aumentar'" @accion="aumentar" />
  </div>
</template>
<script>
import Titulo from "@/components/Titulo";
import Btn from "@/components/Btn";
import { computed, ref } from "vue";
export default {
  components: {
    Titulo,
    Btn,
  },
  setup() {
    const texto = ref("");
    const contador = ref(0);

    const aumentar = () => {
      contador.value++;
    };

    const disminuir = () => {
      contador.value--;
    };

    const color = computed(() => {
      if (contador.value < 0) {
        return "red";
      } else {
        return "blue";
      }
    });

    return {
      contador,
      aumentar,
      disminuir,
      color,
      texto,
    };
  },
};
</script>

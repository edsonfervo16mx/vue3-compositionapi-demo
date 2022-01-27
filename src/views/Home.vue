<template>
  <div class="home">
    <h1 :style="{ color: color }">{{ contador }}</h1>
    <button @click="disminuir">-</button>
    <button @click="aumentar">+</button>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      contador: 0,
    };
  },
  computed: {
    color() {
      if (this.contador < 0) {
        return "red";
      } else {
        return "blue";
      }
    },
  },
  methods: {
    aumentar() {
      this.contador++;
    },
    disminuir() {
      this.contador--;
    },
  },
};
</script>

<template>
  <h1>Lista de paises</h1>
  <p v-for="(pais, index) in arrayData" :key="index">
    {{ pais.name }}
    <router-link :to="`/paises/${pais.name}`">
      {{ pais.name }}
    </router-link>
  </p>
</template>

<script>
import { onMounted, ref } from "vue";
export default {
  setup() {
    const arrayData = ref([]);

    onMounted(async () => {
      try {
        const res = await fetch("https://restcountries.com/v2/all");
        arrayData.value = await res.json();
        console.log(arrayData.value);
      } catch (error) {
        console.log(error);
      }
    });

    /*
    const fetchData = async () => {
      try {
        const res = await fetch("https://restcountries.com/v3.1/all");
        arrayData.value = await res.json();
        console.log(arrayData.value);
      } catch (error) {
        console.log(error);
      }
    };
    fetchData();
    /** */

    return { arrayData };
  },
};
</script>

<style></style>

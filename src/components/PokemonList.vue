<template>
  <ul>
    <li v-for="n in 9" v-bind:key="n">
      <PokemonCard :id="n" />
    </li>
  </ul>
</template>

<script>
import PokemonCard from "./PokemonCard";

export default {
  name: "PokemonList",
  components: {
    PokemonCard
  }
};
</script>
<style>
    ul{list-style:none};
</style>
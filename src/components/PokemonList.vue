<template>
  <div id="list">
    <div v-for="n in 9" v-bind:key="n">
      <PokemonCard :id="n" />
    </div>
  </div>
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
ul {
  list-style: none;
}
</style>
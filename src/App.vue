<template>
  <v-app>
    <v-content>
      <PokemonCard/>
    </v-content>
  </v-app>
</template>

<script>
import PokemonCard from './components/PokemonCard';

export default {
  name: 'App',

  components: {
    PokemonCard,
  },

  data: () => ({
    //
  }),
};
</script>

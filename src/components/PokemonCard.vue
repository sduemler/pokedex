<template>
  <div id="pokemon">
    <v-card class="mx-auto mt-5" max-width="599" raised>
      <div class="d-block-flex">
        <v-list-item-avatar class="d-inline-flex" tile size="150" color="grey lighten-2">
          <v-img :src="info.sprites.front_default" />
        </v-list-item-avatar>

        <v-list-item three-line class="d-inline-flex align-self-start">
            <v-list-item-content>
                <v-list-item-title class="headline mb-1">{{info.name | capitalize}}</v-list-item-title>
            </v-list-item-content>
        </v-list-item>
      </div>

      <div class="d-block-flex">
        <v-list-item three-line>
          <v-list-item-content>
            <div class="overline mb-4">#{{info.id}}</div>
            <v-list-item-title class="headline mb-1">{{info.types[0].type.name | capitalize}} type</v-list-item-title>
            <v-list-item-subtitle>First appeared in Pokemon {{info.game_indices[0].version.name | capitalize}}</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </div>
    </v-card>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "Pokemon",
  data() {
    return {
      info: []
    };
  },
  created() {
    axios.get("https://pokeapi.co/api/v2/pokemon/charmander")
      .then(response => {
        this.info = response.data;
      })
      .catch(e => {
        console.log(e);
      });
  },
  filters: {
    capitalize: function(value) {
      if (!value) return "";
      value = value.toString();
      return value.charAt(0).toUpperCase() + value.slice(1);
    }
  }
};
</script>
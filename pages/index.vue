<template>
  <div class="container">
    <SearchPokemon v-on:search-text='created'/>
    <Pokemons
      v-for="pokemon in pokemons"
      :key="pokemon.url"
      :pokemon="pokemon.name"
      :id="pokemon.url"
    />
  </div>
</template>

<script>
import Axios from "axios";
import Pokemons from "../components/Pokemons";
import SearchPokemon from "../components/SearchPokemon"

export default {
  components: {
    SearchPokemon,
    Pokemons,
  },
  data() {
    return {
      pokemons: [],
    };
  },
  
  methods:{
    async created() {
    const config = {
      headers: {
        Accepts: "application/json",
      },
    };

    try {
      const res = await Axios.get(`https://pokeapi.co/api/v2/pokemon/`, config);

      this.pokemons = res?.data?.results;
      console.log(res?.data?.results);
    } catch (error) {
      console.log("error", error);
    }
  },
  },
  head() {
    return {
      title: "Pokemon",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Searching Pokemon",
        },
      ],
      link: [
        { rel: "icon", type: "image/x-icon", href: "/favicon.png?v=3" },
        {
          rel: "stylesheet",
          type: "text/css",
          href:
            "https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/css/bootstrap.min.css",
        },
      ],
    };
  },
};
</script>

<style></style>

<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <Title message="I pokemon di Classe 22"/>
    <Cards :cards="pokemons" />
    <Cards :cards="players" />
    <!-- <ul>
      <li v-for="(pokemon,index) in pokemons" :key="index">
        <a :href="pokemon.url" target="_blank">{{ pokemon.name }}</a>
      </li>
    </ul> -->
  </div> 

</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Title from "./components/Title.vue";
import Cards from "./views/Cards.vue";
export default {
  name: "App",
  components: {
    // HelloWorld
    Title,
    Cards
  },
  data(){
    return{
      pokemons:[],
      players:[
        {
          "name":"Roberto Baggio",
          "url":"url1"
        },
        {
          "name":"Francesco Totti",
          "url":"url2"
        }
      ],
    }
  },
  mounted(){
    this.axios
    .get(this.base_url + "/pokemon")
    .then((response)=>{
      console.log(response.data);

      this.pokemons=response.data.results;
    });
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul {
  list-style:none;
  margin:0;
}
</style>

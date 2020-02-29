<template>
  <div id="app">
    <h1>Welcome to Studio Ghibli</h1>
    <h2>Films</h2>
    <films-list :films='films'></films-list>
  </div>
</template>

<script>
import FilmsList from './components/FilmsList.vue'

export default {
  name: 'App',
  data() {
    return {
      films: [],
      selectedFilm: null
    };
  },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)

},

components: {
  'films-list': FilmsList,
  'film-item':FilmItem
}

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

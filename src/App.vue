<template lang="html">
  <div>

<h1>Studio Ghibli</h1>
<films-list :films='films'></films-list>
<film-detail :film='selectedFilm'></film-detail>
    </div>
</template>


<script>
import FilmsList from './components/FilmsList.vue'
import FilmDetail from './components/FilmDetail.vue'

import {eventBus} from './main.js'

export default {
  name:'app',
  data(){
    return{
      films: [],
      selectedFilm: null
    };
  },
  mounted(){
  fetch('https://ghibliapi.herokuapp.com/films')
  .then(res => res.json())
  .then(films => this.films = films)

  eventBus.$on('film-selected', (film)=> {
    this.selectedFilm = film;
  })
},
  components: {
    "films-list": FilmsList,
    "film-detail": FilmDetail

  }
}
</script>

<style lang="css" scoped>
</style>

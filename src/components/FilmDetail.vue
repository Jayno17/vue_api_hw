<template lang="html">
<div class="film-detail" v-if="film">
  <h3>{{film.title}}</h3>
  <p>Description: {{film.description}}</p>
  <p>Director: {{film.director}}</p>
  <p>Release date: {{film.release_date}}</p>

</div>
</template>

<script>
import {eventBus} from '../main.js'
export default {
  name: 'fim-detail',
  props: ['film']
}
</script>

<style lang="css" scoped>
</style>

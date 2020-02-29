<template lang="html">
<ul>
  <film-item v-for="film in films" :film="film"></film-item>
</ul>
</template>

<script>

import FilmItem from './FilmItem.vue'

export default {
  name: 'films-list',
  props: ['films'],
  components: {
    'film-item': FilmItem,
  }
}
</script>

<style lang="css" scoped>
</style>

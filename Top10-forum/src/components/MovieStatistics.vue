<template>
  <h2>Statistics</h2>
  <ul>
    <li v-for="(stat, type) in movieStatistics" :key="`movie-${type}-${stat}`">
      {{ type }}: {{ stat }}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'MovieStatistics',
  props: {
    movies: {
      type: Array,
      required: true
    }
  },
  data: () => ({}),

  computed: {
    movieStatistics() {
      const genres = ['Documentary', 'Drama', 'War']
      const statistics = {
        Documentary: 0,
        Drama: 0,
        War: 0
      }
      this.movies.forEach((movie) => {
        genres.forEach((genre) => {
          if (movie.Genre.indexOf(genre) > -1) {
            statistics[genre] += 1
          }
        })
      })
      return statistics
    }
  }
}
</script>

<style></style>

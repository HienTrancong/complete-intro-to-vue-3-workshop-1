<template>
  <BaseLayout>
    <template v-slot:two>
      <MovieStatistics :movies="movieList" />
    </template>
  </BaseLayout>

  <h2>Movies list</h2>
  <ul v-if="movieList.length > 0">
    <li v-for="(movie, index) in movieList" :key="`movie-${index}`">
      <div>
        <span>{{ movie.Title }}</span>
      </div>
      <button @click="addFavorite(movie)">&star; Favorite</button>
    </li>
  </ul>
  <p v-else>There are no movie to show</p>
  <!-- <MovieList /> -->
  <h2>Favorite movies list</h2>
  <ul v-if="favoriteMovieList.length > 0">
    <li v-for="(movie, index) in favoriteMovieList" :key="`movie-${index}`">{{ movie.Title }}</li>
  </ul>
  <p v-else>No favorite movie yet!</p>

  <h2>Add new movie</h2>
  <pre>{{ newMovie }}</pre>
  <div>
    <label for="movie-title">Movie Title</label>
    <input type="text" v-model="newMovie.Title" @keyup.enter="addMovie(newMovie)" />
  </div>
</template>

<script>
import MovieStatistics from './components/MovieStatistics.vue'
import BaseLayout from './components/BaseLayout.vue'

export default {
  components: {
    MovieStatistics,
    BaseLayout
  },
  data: () => ({
    movieList: [
      { Title: 'Mayor', Genre: ['Documentary', 'Drama'] },
      { Title: 'Paper Spiders', Genre: ['Drama'] },
      { Title: 'Quo Vadis, Aida', Genre: ['War'] },
      { Title: 'Luzzu', Genre: ['Drama'] }
    ],
    favoriteMovieList: [],
    newMovie: {
      name: ''
    }
  }),

  methods: {
    addFavorite(movie) {
      this.favoriteMovieList.push(movie)
    },
    addMovie(movie) {
      this.movieList.push(this.newMovie)
      this.newMovie = {
        name: ''
      }
    }
  }
}
</script>

<style></style>

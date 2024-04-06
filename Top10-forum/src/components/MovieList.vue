<!-- <template>
  <h2>Movies list</h2>
  <ul v-if="movieList.length > 0">
    <li v-for="(movie, index) in movieList" :key="`movie-${index}`">
      <div>
        <span>{{ movie.Title }}</span>
        <button @click="addFavorite(movie)">&star; Favorite</button>
      </div>
    </li>
  </ul>
  <p v-else>There are no movie to show</p>
</template>

<script>
export default {
  data: () => ({
    movieList: [
      { Title: 'Mayor', Genre: ['Documentary', 'Drama'] },
      { Title: 'Paper Spiders', Genre: ['Drama'] },
      { Title: 'Quo Vadis, Aida', Genre: ['War'] },
      { Title: 'Luzzu', Genre: ['Drama'] }
    ],
    favoriteMovieList: []
  }),
  methods: {
    addFavorite(movie) {
      this.favoriteMovieList.push(movie)
    }
  }
}
</script>
<style></style> -->

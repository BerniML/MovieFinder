<template>
  <div class="col-5 text-center">
    <b-form-group horizontal description="Search for a movie">
      <b-form-input
        v-on:keyup.enter="homeSearchRequest"
        v-model="movies.searchInput"
      ></b-form-input>
    </b-form-group>
    <b-button type="submit" variant="primary" @click="homeSearchRequest">Submit</b-button>
  </div>
</template>

<script>
import { mapState, mapActions } from 'vuex'

export default {
  name: 'HomeSearch',
  computed: {
    ...mapState(['search'])
  },
  data () {
    return {
      movies: {
        searchInput: ''
      }
    }
  },
  methods: {
    ...mapActions([
      'movieTitleRequest' // perform request to movie API
    ]),
    async homeSearchRequest () {
      await this.movieTitleRequest(this.movies.searchInput)
      this.$router.push('/movies')
    }
  }
}
</script>

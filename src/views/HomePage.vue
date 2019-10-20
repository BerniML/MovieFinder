<template>
  <div id="HomePage">
    <b-jumbotron>
      <template v-slot:header>
        <div class="row justify-content-center">MovieFinder</div>
      </template>

      <b-container>
        <hr class="my-4" />
        <div
          class="row justify-content-center"
        >Search app for searching movies and series, displaying the title, year, poster and director!</div>

        <div class="row justify-content-center mt-3">
          <HomeSearch />
        </div>
      </b-container>
    </b-jumbotron>
    <Recommendations />
  </div>
</template>

<script>
import HomeSearch from '@/components/HomeSearch.vue'
import Recommendations from '@/components/Recommendations.vue'
export default {
  name: 'HomePage',
  components: {
    HomeSearch,
    Recommendations
  }
}
</script>

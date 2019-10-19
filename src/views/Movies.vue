<template>
  <div id="movieContainer" class="mt-5">
    <b-container>
      <div class="row justify-content-center">
        <div class="col text-center">
          <slider></slider>
          <b-alert
            class="mt-5 center-block"
            v-show="search.emptyResults"
            show
            variant="warning"
          >I'm sorry, no movies found with this title, please try again!</b-alert>
        </div>
      </div>
    </b-container>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import Slider from '@/components/Slider.vue'

export default {
  name: 'Movies',
  components: {
    Slider
  },
  computed: {
    ...mapState(['movieQuery', 'search'])
  },
  mounted () {
    // If the user did not perform  any search
    if (!this.movieQuery) {
      this.$router.push({ name: 'home' })
    }
  }
}
</script>
<style scoped>
.alert {
  width: 50%;
  display: inline-block;
  margin: 0 auto;
}
</style>

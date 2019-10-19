<template>
    <div id="slider" v-show="!search.emptyResults">
      <b-carousel
        id="carousel-1"
        v-model="slide"
        :interval="4000"
        controls
        indicators
        background="#ababab"
        img-width="1024"
        img-height="480"
        style="text-shadow: 1px 1px 2px #333; max-width:900px; max-height:600px !important;"
        :img-blank="true"
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
      >

        <b-carousel-slide
            :caption="search.results.title"
            :text-html="movieSubtitle"
          >
          <template v-slot:img>
            <img
              class="d-block"
              width="1024"
              height="480"
              :src="search.results.poster"
              alt="image slot"
            />
          </template>
        </b-carousel-slide>
      </b-carousel>
    </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'Slider',
  data () {
    return {
      slide: 0,
      sliding: null
    }
  },
  methods: {
    onSlideStart (slide) {
      this.sliding = true
    },
    onSlideEnd (slide) {
      this.sliding = false
    }
  },
  computed: {
    ...mapState(['search']),
    movieSubtitle () {
      return this.search.results.director + '<p>' + this.search.results.year + '</p>'
    }
  }
}
</script>
<style>
.carousel-inner > .item > img {
  width:640px!important;
  height:360px!important;
}
</style>

<template>
  <div id="loveToKnow">
    <Header />
    <ConnexionError v-if="connexionError"/>
    <router-view />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import ConnexionError from '@/components/ConnexionError.vue'
import { mapState } from 'vuex'

export default {
  name: 'MovieFinder',
  components: {
    Header,
    ConnexionError
  },
  computed: {
    ...mapState(['connexionError'])
  }
}
</script>

<template>
  <div id="loveToKnow">
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
export default {
  name: 'MovieFinder',
  components: {
    Header
  }
}
</script>

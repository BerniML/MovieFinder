<template>
  <b-alert show variant="danger" class="mb-0">{{ConnexionErrorMessage}}</b-alert>
</template>

<script>

export default {
  name: 'ConnexionError',
  data () {
    return {
      ConnexionErrorMessage: 'Something went wrong! please try again'
    }
  }
}
</script>

<template>
  <div class="test container">
    <h1>Riot API</h1>
    <formulaire></formulaire>
    <div class="row">
    </div>
  </div>
</template>

<script>
import Formulaire from './Formulaire.vue'
import Summoner from './Summoner.vue'
export default {
  name: 'app',
  components: {
    Formulaire,
    Summoner
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style>
</style>

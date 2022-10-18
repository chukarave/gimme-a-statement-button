<template>
  <img class="wikidata-logo" alt="Wikidata logo" src="./assets/Wikidata-logo.svg">
  <div class="statement-button">
     <statement-button />
  </div>
</template>

<script>
import StatementButton from './components/StatementButton.vue'

export default {
  name: 'App',
  components: {
    StatementButton
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.wikidata-logo {
  height: 226px;
  width: 320px;
}
</style>

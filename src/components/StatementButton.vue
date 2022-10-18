<template>
  <button class="statment-getter" @click="fetchClaims">Get me a statement!</button>
  <div v-if=showClaim>
    <h1 class="display-claim" v-for="claim in claimsArray" :key="claim.mainsnak">{{ claim }}</h1>
  </div>
</template>

<script>

export default {
  data() {
    return {
      showClaim: false,
      claimsArray: []
    }
  },
  /*,
  mounted(){
      const parsedData = JSON.parse(this.claimsArray);
      this.claimsArray = parsedData.claimsArray
  },*/

  methods : {
    fetchClaims: function(){
      fetch('https://www.wikidata.org/w/api.php?action=wbgetclaims&format=json&entity=Q42&entity=Q42&property=P31&formatversion=latest&origin=*')
      .then((response) => response.json())
      .then(data => (this.claimsArray = JSON.stringify( data.claims)))
      .catch(err => console.log(err.message))

      console.log(this.claimsArray);
      this.showClaim = true;
    }
  }
}
</script>

<style>
.statment-getter {
  height: 52px;
  width: 250px;
  margin-top: 40px;
  font-size: medium;
  font-family: sans-serif;
}
</style>
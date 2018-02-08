<template lang="html">
  <div class="container">
    <div class="form-group">
      <label >Summoner Name</label>
      <input v-model="sumName" type="text" class="form-control" id="summonerName" placeholder="Enter a summoner name">
      <img v-bind:src="imgUrl" alt="">
    </div>
    <div class="form-group">
         <label for="inputState">Server</label>
         <select id="inputState" class="form-control">
           <option selected>EUW</option>
           <option>NA</option>
         </select>
       </div>
    <div class="form-check">
      <input type="checkbox" class="form-check-input" id="exampleCheck1">
      <label class="form-check-label" for="exampleCheck1">Check me out</label>
    </div>
    <button @click="apiRiot" id="summonerSub" type="submit" class="btn btn-primary">Submit</button>
    <p>{{ sumInfo }}</p>
    <div class="card" style="width: 18rem;">
    <img class="card-img-top" src="./assets/téléchargement.svg" alt="Card image cap">
    <div class="card-body">
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    </div>
  </div>
  <p>
    {{ dataIcon }}
  </p>
    </div>
</template>

<script>
export default {
  data() {
    return {
      sumName: "",
      sumInfo: "",
      imgUrl: "",
      ddragonLink: 'http://ddragon.leagueoflegends.com/cdn/6.24.1/img/profileicon/',
      dataIcon: ""
    }
  },
  methods: {
    apiRiot: function () {
      const proxyurl = "https://cors-anywhere.herokuapp.com/"
      const APIKEY = 'RGAPI-ab2455c5-073e-455f-97b2-83bf8f6e64b1'
      let url = `https://euw1.api.riotgames.com/lol/summoner/v3/summoners/by-name/${this.sumName}`
      let uri = `${url}?api_key=${APIKEY}`
      uri = proxyurl+uri

      fetch(uri).then( response => {
        return response.json()
      }).then( data => {
        this.sumInfo = data
        this.imgUrl = data
      }
      ).catch(error => console.error(error))


    }
  }
}
</script>

<style lang="css">
</style>

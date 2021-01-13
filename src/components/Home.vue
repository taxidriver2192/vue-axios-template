<template>
  <div class="home">
    <div class="title">
      <div class="container">
      <h1>{{ title }}</h1>
      </div>
      <img class="wave" src="./../assets/images/wavewhite.svg">
    </div>
    
    <div class="answer">
      <div class="container">
        <h2>Her er alle Items</h2>
        <pre>{{ items }}</pre>
        <a class="button" @click="loadData">Press me</a>
      </div>
    </div>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Start',
  data () {
    return {
      items: [],
      api_url: 'https://exsametestapp.azurewebsites.net/api/Item'
    }
  },
  props: {
    title: String
  },
  methods: {
    loadData: function() {
      axios.get(this.api_url) // returns a promise
        .then(response => {
          this.items = response.data
          console.log(this.items)
        }).catch(err => {
          alert('Error while trying to call the api: ' + err)
        })
    }
  },
  mounted() {
    this.loadData()
  }
}
</script>

<style scoped>
.title {
  background: #5865FF;
  color: #ffffff;
}
.title h1 {
  margin: 0 0 .5rem 0;
  font-size: 3.5rem;
}
.title p {
  font-size: 1.25rem;
}
.button {
  color: #ffffff;
  font-weight: 600;
  background: #5865FF;
  border-radius: .25rem;
  display: inline-block;
  padding: 1rem 2rem;
  text-decoration: none;
  box-shadow: 0 .25rem 0 rgba(0,0,0, 0.1);
  outline: none;
  border: none;
  font-size: 1rem;
  transition: all 0.2s ease;
  margin: 1rem 0 3rem 0;
  cursor: pointer;
}
.button:hover{
  transform: scale(1.1);
}
.wave {
  margin-top: 10vw;
  margin-bottom: -1rem;
  width: 100%;
}
.answer {
  text-align: center;
  background: #ffffff;
  color: #5865FF;
}
.answer img {
  max-height: 300px;
  max-width: 100%;
  margin: 1rem auto;
  border-radius: .5rem;
}
.answer h2 {
  font-size: 2.5rem;
}
</style>

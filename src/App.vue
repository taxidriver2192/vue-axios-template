<template>
  <div id="app">
    <header class="app-header">
    </header>
    <Home :title="title"/>
  </div>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'app',
  components: {
    Home
  },
  data () {
    return {
      title: 'Vue Opgave done! 🚀'
    }
  }
}
</script>

<style>
html {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smothing: grayscale;
}

* {
  border: 0;
  padding: 0;
  margin: 0;
}

body {
  font-family: "Nunito Sans", sans-serif;
  color: #5865FF;
  font-size: 17px;
}

.container {
  margin: 0 auto;
  max-width: 800px;
  padding: 0 1.5rem;
}
.logo {
  display: block;
}
.app-header {
  background: #5865FF;
  padding: 2.5rem 0;
}

</style>

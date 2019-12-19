<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/Unknown.jpg">
    <HelloWorld :msg='quote'/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  data(){
    return {
      quote: ''
    }
  },
  name: 'app',
  components: {
    HelloWorld
  },
  mounted(){
    
    setInterval((this.axios.get('http://188.225.47.187/api/cats/random-fact.php'))
    .then((responce) => { this.quote=responce.data; }), 10)
    
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

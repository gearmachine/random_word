<template>
  <div id="app">
    {{random(verbs)}} <br>
    {{random(adjs)}}
  </div>
</template>

<script>
import verb from 'raw-loader!./assets/verb.txt';
import adj from 'raw-loader!./assets/adjective.txt';

export default {
  name: 'app',
  data() {
    return {
      verbs: null,
      adjs: null
    }
  },
  methods : {
    random(array){
      let length = Math.min(500, array.length);
      let index = Math.round( Math.random()* length );
      return array[index];
    }
  },
  created() {
    this.verbs = verb.split("\r\n");
    this.adjs = adj.split("\r\n");
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

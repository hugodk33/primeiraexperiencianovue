<template>
  <div id="app" class="container">
    <div class="row">
      <div class="col-md-8 text-center" style="margin: 0 auto">
        <Manchete v-bind:manchete="manchete" v-bind:corpo="corpo" />
        
      </div>
      <div class="col-md-8 text-center" style="margin: 0 auto">
        <Btn v-on:mudaManchete="chamaapi()" />
      </div>
    </div>
  </div>
</template>

<script>

import Manchete from './components/Manchete.vue'
import Btn from './components/Btn.vue'

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

export default {
  name: 'App',
  components: {
    Manchete,
    Btn
  },
  methods: {
    chamaapi: function() {
      this.$http.get('https://jsonplaceholder.typicode.com/posts/1').then((response) => response.json()).then((json) => this.atualiza(json))
    },
    atualiza: function(val) {
      this.manchete = val.title
      this.corpo = val.body
    }
  },
  data: function() {
    return {
      corpo: "",
      manchete: "Clique e veja a Manchete de Hoje"
    }
  }
}

</script>

<style>
h1 {
  color: black
}
</style>

<style lang="scss">
  @import './assets/styles/variables';
  @import './assets/styles/bootstrap';
</style>

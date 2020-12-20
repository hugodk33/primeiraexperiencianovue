<template>
  <div>
    <button v-on:click="Teste">CHAMAR API :)</button>
  </div>
</template>

<script>

export default {
  name: 'Lista',
  methods: {
    Teste: function(){
      this.$emit("mudaManchete" , null)
    }
  }
}

</script>
<style scoped>

</style>

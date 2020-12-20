<template>
  <div class="Manchee" style="padding-top: 50px">
    <h3>{{manchete}}</h3>
    <p>{{corpo}}</p>
  </div>
</template>

<script>
export default {
  name: 'Input',
  props: {
    manchete: String,
    corpo: String
  }
}
</script>

<style scoped>
  h3 {
    color: black;
  }
  p {
    color: black
  }
</style>
"
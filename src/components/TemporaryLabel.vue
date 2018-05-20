<template>
  <div class="label">
      Temporary Kitten Version
  </div>
</template>

<script>
  export default {
    name: 'temporary-label'
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import url('https://fonts.googleapis.com/css?family=Permanent+Marker');

  .label {
    position: absolute;
    white-space: nowrap;
    bottom: 15%;
    background: white;
    padding: 4px 8px;
    font-size: 12px;
    left: 30%;
    transform: rotate(-9deg);
    font-family: "Permanent Marker";
    border: 2px double black;
  }
</style>

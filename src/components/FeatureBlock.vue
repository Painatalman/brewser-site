<template>
  <div class="feature-block">
    <p class="title" v-if=title>
      {{ title }}
    </p>
    <slot></slot>
  </div>
</template>

<script>

export default {
  name: 'featureBlock',
  props: ['title']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

@font-face {
  font-family: 'Tungsten';
  src: url('../assets/Tungsten-Light.otf') format('opentype');
  font-weight: 300;
  font-style: normal;
}

.title {
  text-transform: uppercase;
  font-family: 'Tungsten', sans-serif;
  font-weight: 300;
  color: rgb(229, 51, 42);
  font-size: 33px;
  line-height: 34px;
}

</style>

<template>
  <section class="card">
    <header>
      <h3 class="title">{{ title }}</h3>
    </header>
    <slot></slot>
    <Footer></Footer>
  </section>
</template>

<script>
import Footer from '@/components/Footer'

export default {
  name: 'card',
  components: {
    'Footer': Footer
  },
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

.card {
  border: 1px solid black;
  padding: 24px;
  margin: 24px;
  max-width: 340px;

  text-align: center;
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

<template>
  <header :style="style">
    <div class="logo-container">
      <img class="logo" src="../assets/logo.png" alt="logo">
      <TemporaryLabel></TemporaryLabel>
    </div>
    <h2 v-if="subtitle">
      {{ subtitle }}
    </h2>
  </header>
</template>

<script>
  import TemporaryLabel from '@/components/TemporaryLabel.vue'

  export default {
    name: 'column',
    components: {
      'TemporaryLabel': TemporaryLabel
    },
    props: ['subtitle'],
    data: function () {
      return {
        style: {
          flex: this.flex || 1,
          marginTop: '16px',
          textAlign: 'center'
        }
      }
    }
  }
</script>
<style scoped>
  h2 {
    font-size: 40px;
    text-transform: uppercase;
    color: rgb(229, 51, 42);
  }

  .logo-container {
    position: relative;
    display: inline-block;
  }
</style>
<template>
  <div class="col" :style="style">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'column',
    props: ['flex'],
    computed: {
      style: function () {
        return {
          flex: this.flex || 1
        }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @media (max-width: 768px) {
    .col {
      padding: 12px 24px;
      text-align: center;
    }
  }
</style>

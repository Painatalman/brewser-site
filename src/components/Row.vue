<template>
  <div class="row">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'row'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 1200px;
    margin: auto;
  }

  @media (max-width: 1199px) {
    .row {
      max-width: 992px;
    }
  }

  @media (max-width: 768px) {
    .row {
      flex-direction: column;
    }
  }
</style>

<template>
  <header :style="style">
    <div class="logo-container">
      <img class="logo" src="../assets/logo.png" alt="logo">
    </div>
    <slot></slot>
  </header>
</template>

<script>
  export default {
    name: 'column',
    data: function () {
      return {
        style: {
          flex: this.flex || 1,
          position: 'relative'
        }
      }
    }
  }
</script>

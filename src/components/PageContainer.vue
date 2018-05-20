<template>
  <div :style="style">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'pageContainer',
    data: function () {
      return {
        style: {
          display: 'flex',
          alignItems: 'space-between',
          height: '100%',
          flexDirection: 'column'
        }
      }
    }
  }
</script>

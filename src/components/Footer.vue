<template>
  <footer :style="style">
    <div class="download-buttons">
      <img class="download-button" src="../assets/google-play-badge.png" alt="download on app store">
      <div class="download-button" role="button" v-html="require('@/svg/app-store-badge.svg')">
      </div>
    </div>
    <slot></slot>
  </footer>
</template>

<script>
  export default {
    name: 'main-footer',
    data: function () {
      return {
        style: {
          flex: this.flex || 1
        }
      }
    }
  }
</script>

<style scoped>
.download-buttons {
  display: flex;
  align-items: center;
}

.download-button {
  width: 120px;
  margin: 12px;
}
</style>

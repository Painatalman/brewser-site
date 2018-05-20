<template>
  <div class="cover">
    <div v-html="require('@/svg/phone.svg')"></div>
    <slider 
      animation="fade"
      width="88%"
      height="0"
      ctrl-btn="false"
      indicators="false"
    >
      <slider-item>
        <img src="http://placekitten.com/g/211/336">
      </slider-item>
      <slider-item>
        <img src="http://placekitten.com/211/336">
      </slider-item>
    </slider>
  </div>
</template>

<script>
import { Slider, SliderItem } from 'vue-easy-slider'

export default {
  name: 'phone-picture',
  components: {
    'slider': Slider,
    'slider-item': SliderItem
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .cover {
    position: relative;
    display: block;
    margin: auto;
    width: 240px;
  }
  .slider {
    position: absolute;
    top: 15.4%;
    left: 50%;
    transform: translateX(-50%);
    padding-bottom: 140.2%;
    overflow: hidden;
  }

</style>

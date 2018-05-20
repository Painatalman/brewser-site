<template>
  <div class="splashscreen">
    <PageContainer>
      <Row>
        <Column>
          <Header>
            <TemporaryLabel></TemporaryLabel>
          </Header>
        </Column>
      </Row>
      <Row ref="mainRow" style="opacity: 0">
        <Column :flex="flexSides">
          <FeatureBlock :title="leftTitle">
            <p>
              With more than 150 kittens already on our catalogue, we have the
              fastest growing album of professionally photographed kittens on a mobile APP.
            </p>
          </FeatureBlock>
        </Column>
        <Column :flex="flexCenter">
          <PhonePicture></PhonePicture>
        </Column>
        <Column :flex="flexSides">
          <FeatureBlock
            :title=rightTitle
          >
            <div class="gallery">
              <img class="gallery__image" src="http://placekitten.com/300/200" alt="placeholder kitten">
              <img class="gallery__image" src="http://placekitten.com/300/200" alt="placeholder kitten">
              <img class="gallery__image" src="http://placekitten.com/300/200" alt="placeholder kitten">
              <img class="gallery__image" src="http://placekitten.com/300/200" alt="placeholder kitten">
              <img class="gallery__image" src="http://placekitten.com/300/200" alt="placeholder kitten">
              <img class="gallery__image" src="http://placekitten.com/300/200" alt="placeholder kitten">
            </div>
          </FeatureBlock>
        </Column>
      </Row>
      <Row>
        <Column>
          <Footer></Footer>
        </Column>
      </Row>
    </PageContainer>
  </div>
</template>

<script>

import PageContainer from '@/components/PageContainer.vue'
import Row from '@/components/Row.vue'
import Column from '@/components/Column.vue'
import FeatureBlock from '@/components/FeatureBlock.vue'
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import PhonePicture from '@/components/PhonePicture.vue'
import TemporaryLabel from '@/components/TemporaryLabel.vue'

import { TimelineLite } from 'gsap'

export default {
  name: 'home',
  components: {
    'PageContainer': PageContainer,
    'Column': Column,
    'Footer': Footer,
    'Row': Row,
    'FeatureBlock': FeatureBlock,
    'Header': Header,
    'PhonePicture': PhonePicture,
    'TemporaryLabel': TemporaryLabel
  },
  data: function () {
    return {
      leftTitle: 'Search and discover your favourite kittens',
      rightTitle: 'Some of the kittens that have already joined us',
      flexSides: 3,
      flexCenter: 4,
      flexRight: 3
    }
  },
  mounted: function () {
    const tl = new TimelineLite()

    tl.fromTo(this.$refs.mainRow.$el, 5, {opacity: 0}, {opacity: 1})

    if (Notification.permission === 'default') {
      Notification.requestPermission()
        .then(
          result => (result === 'granted') && new Notification('Thank you for subscribing to Brewer!')
        )
    } else {
      (Notification.permission === 'granted') && new Notification('Welcome to the Homepage!')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@font-face {
  font-family: 'Tungsten';
  src: url('../assets/Tungsten-Bold.otf') format('opentype');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'Tungsten';
  src: url('../assets/Tungsten-Light.otf') format('opentype');
  font-weight: 300;
  font-style: normal;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #35495E;
}

.splashscreen {
  background-image: url('../assets/fundo.jpg');
  background-size: cover;
  height: 100vh;
}

@media (max-width: 768px) {
  .splashscreen {
    height: auto;
  }
}

.gallery {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
}

.gallery__image {
  width: 30%;
  margin-bottom: 12px;
}

</style>

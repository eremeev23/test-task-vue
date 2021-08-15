<template>
  <div id="app">
      <Header />
      <Gallery 
        :gallery_data='carouselSlides'
        :interval="10000"
      /> 
      <Features />
      <Intro />
  </div>
</template>

<script>
import Header from '@/components/Header';
import Gallery from '@/components/Gallery';
import Features from '@/components/Features';
import Intro from '@/components/Intro';

export default {
  name: 'app',
  components: {
    Header,
    Gallery,
    Features,
    Intro
  },
  data() {
    return {
      carouselSlides: [
        {id: 1, name: 'img1', img: '6.png'},
        {id: 2, name: 'img2', img: '6.png'},
        {id: 3, name: 'img3', img: '6.png'},
        {id: 4, name: 'img4', img: '6.png'},
        {id: 5, name: 'img5', img: '6.png'}
      ]
    }
  },
}
</script>

<style>
@font-face {
    font-family: 'Bw Modelica';
    src:url('./assets/BwModelicaCyrillicDEMO-Medium.woff2') format('woff2'),
        url('./assets/BwModelicaCyrillicDEMO-Medium.woff') format('woff'),
        url('./assets/BwModelicaCyrillicDEMO-Medium.ttf') format('truetype');
    font-weight: 500;
    font-style: normal;
}
@font-face {
    font-family: 'Bw Modelica';
    src:url('./assets/BwModelicaCyrillicDEMO-ExtraBold.woff2') format('woff2'),
        url('./assets/BwModelicaCyrillicDEMO-ExtraBold.woff') format('woff'),
        url('./assets/BwModelicaCyrillicDEMO-ExtraBold.ttf') format('truetype');
    font-weight: 800;
    font-style: bold;
  }

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Bw Modelica';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>

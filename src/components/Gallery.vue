<template>
  <div class="wrapper">
    <div class="gallery" :style="{'margin-left': '-' + (100 * currentSlideIndex) + '%'}">
      <Slide v-for='item in gallery_data'
        :key='item.id'
        :item_data="item"
       />
      <div class="pagination">
        <span
          class="dot"
          v-for="slide in gallery_data"
          :key='slide.id'
          :class="{'active': isActive === slide.id - 1}"
          @click="isActive = currentSlideIndex = slide.id - 1"
        >
        </span>
      </div>
    </div>
    <button @click="prevSlide" class="btn btn__prev"><i class="fas fa-chevron-left"></i></button>
    <button @click="nextSlide" class="btn btn__next"><i class="fas fa-chevron-right"></i></button>
  </div>
</template>

<script>
import Slide from './Slide'

export default {
  name: 'gallery',
  components: {
    Slide
  },
  props: {
    gallery_data: {
      type: Array,
      default: () => []
    },
    interval: {
      type: Number,
      default: 0
    }
  },
  data(){
        return {
        windowWidth: null,
        currentSlideIndex: 0,
        isActive: 0
        }
    },
  created() {
      window.addEventListener('resize', this.checkScreen);
      this.checkScreen();
    },
  methods: {
      checkScreen(){
          const gallery = document.querySelector('.gallery');
          const wrapper = document.querySelector('.wrapper')
          this.windowWidth = window.innerWidth;
          if(this.windowWidth > 1100){
            gallery.style.height = '400px';
            wrapper.style.height = '400px';
          } else {
          gallery.style.height = `${this.windowWidth / 2.77}px`;
          wrapper.style.height = `${this.windowWidth / 2.77}px`;
          }
          return;
      },
      prevSlide() {
        if(this.currentSlideIndex > 0){
          this.currentSlideIndex--;
          this.isActive--;
        }
      },
      nextSlide() {
        if(this.currentSlideIndex >= this.gallery_data.length - 1){
          this.currentSlideIndex = 0;
          this.isActive = 0;
        } else{
        this.currentSlideIndex++;
        this.isActive++;
        }
      },
  },
  mounted(){
    if(this.interval > 0) {
      let vm = this;
      setInterval (function () {
        vm.nextSlide()
      }, vm.interval)
    }
  }
}
</script>

<style scoped>
.wrapper {
    overflow: hidden;
    position: relative;
    max-height: 440px;
    max-width: 1110px;
    margin: 0 auto;
}
.gallery {
    max-height: 440px;
    display: flex;
    transition: all .8s ease;
}
.btn {
    position: absolute;
    outline: none;
    cursor: pointer;
    color: #497952;
    background: rgba(255, 255, 255, 0.8);
    border: 1px solid #497952;
    border-radius: 50%;
    width: 20px;
    height: 20px;
    transition: all ease .3s;
    padding: 2px;
}
.btn__prev {
    top: 50%;
    left: 20px;
    transform: translateY(-50%);
}
.btn__next {
    top: 50%;
    right: 20px;
    transform: translateY(-50%);
}
.btn:hover {
    background: #497952;
    color: #fff;
}
.pagination {
    position: absolute;
    display: flex;
    justify-content: space-between;
    bottom: 20px;
    width: 170px;
    left: 50%;
    transform: translateX(-50%);
}
.pagination span {
    display: block;
    height: 10px;
    width: 10px;
    cursor: pointer;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.6);
    transition: all .8s ease;
}
.pagination span.active {
    background: #497952;
}
</style>
<template>
  <header>
    <div class="navbar">
      <div>
        <button>Order Online</button>
      </div>
      <nav>
        <div class="menu-left">
          <ul>
            <li>Home</li>
            <li>Pages</li>
            <li>Menu</li>
          </ul>
        </div>
        <div class="logo">
          <img
            src="/img/logo/h5-logo-divided-header.png"
            alt="Don Peppe Logo"
          />
        </div>
        <div class="menu-right">
          <ul>
            <li>Event</li>
            <li>Blog</li>
            <li>Landing</li>
          </ul>
        </div>
      </nav>
      <div class="navbar-right">
        <ul>
          <li>cart</li>
          <li>search</li>
        </ul>
      </div>
    </div>
    <div class="jumbotron">
    <div class="label" @click="prevSlide(jumboSlides.length-1)"><div class="prev"><span>Prev</span></div></div>
    <div>
      <div
        v-for="(jumboSlide, index) in jumboSlides"
        :key="index"
      >
      <div :class="currentIndex === index ? 'jumbo-focus' : 'hide'" :style='{ background: `url("/img/jumbotron/${jumboSlide.textImgPath}.png") no-repeat center` }'>
        <img
        
          :src="`/img/jumbotron/${jumboSlide.pizzaImgPath}.png`"
          alt=""
        />
      </div>
      </div>
    </div>
    <div class="label" @click="nextSlide(jumboSlides.length-1)"><div class="next"><span>Next</span></div></div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderApp',
  data() {
    return {
      currentIndex:0
    }
  },
  props: {
    jumboSlides: Array,
  },
  methods: {
    prevSlide(iMax) {
      if (this.currentIndex <= 0) {
        this.currentIndex = iMax
      } else {
        this.currentIndex--
      }
    },
    nextSlide(iMax) {
      if (this.currentIndex >= iMax) {
        this.currentIndex = 0
      } else {
        this.currentIndex++
      }
    },
  },
}
</script>

<style scoped lang="scss">
@import '@/style/header.scss';
</style>

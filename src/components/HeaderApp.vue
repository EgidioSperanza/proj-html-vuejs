<template>
  <header id="top">
    <nav>
      <button>Order Online</button>
      <div class="menu">
        <ul>
          <li class="home">
            <img
              class="default"
              src="/img/svg/svg-0.svg"
              alt="Don Peppe Baffo"
            />
            <img class="hover" src="/img/svg/svg-2.svg" alt="Don Peppe Baffo" />
            Home
          </li>
          <li @click.prevent="$emit('scrollTo', '#testimonials')">Pages</li>
          <li @click.prevent="$emit('scrollTo', '#menu')">Menu</li>
        </ul>
      </div>
      <img
        class="logo"
        src="/img/logo/h5-logo-divided-header.png"
        alt="Don Peppe Logo"
      />
      <div class="menu">
        <ul>
          <li @click.prevent="$emit('scrollTo', '#events')">Event</li>
          <li>Blog</li>
          <li>Landing</li>
        </ul>
      </div>
      <div class="cart">
        <ul class="right">
          <li class="cart-link">
            <img class="cart-ico" src="/img/svg/svg-1.svg" alt="your Cart" />
            cart
            <div class="current-cart">0</div>
          </li>
          <li>
            <i class="fas fa-search"></i>
            search
          </li>
        </ul>
      </div>
    </nav>
    <div class="jumbotron">
      <div class="label" @click="prevSlide(jumboSlides)">
        <div class="prev"><span>Prev</span></div>
      </div>
      <div>
        <div v-for="(jumboSlide, index) in jumboSlides" :key="index">
          <div
            :class="currentIndex === index ? 'jumbo-focus' : 'hide'"
            :style="{
              background: `url(&quot;/img/jumbotron/${jumboSlide.textImgPath}.png&quot;) no-repeat center`,
            }"
          >
            <img
              :src="`/img/jumbotron/${jumboSlide.pizzaImgPath}.png`"
              alt=""
            />
          </div>
        </div>
      </div>
      <div class="label" @click="nextSlide(jumboSlides)">
        <div class="next"><span>Next</span></div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderApp',
  data() {
    return {
      currentIndex: 0,
    }
  },
  props: {
    jumboSlides: Array,
  },
  methods: {
    prevSlide(iMax) {
      if (this.currentIndex <= 0) {
        this.currentIndex = iMax.length - 1
      } else {
        this.currentIndex--
      }
    },
    nextSlide(iMax) {
      if (this.currentIndex >= iMax.length - 1) {
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

<template>
  <section class="testimonials-section">
    <div class="label" @click="prevSlide(lastTestimonials().length - 1)">
      <div class="prev">
        <span>Prev</span>
      </div>
    </div>
    <div class="testimonial">
      <div v-for="(testimonial, index) in lastTestimonials()" :key="index">
        <div :class="currentIndex === index ? 'testimonial-target' : 'hide'">
          <p class="quotes"><i class="fas fa-quote-left"></i></p>
          <p>{{ testimonial.text }}</p>
          <p class="testimonial-author">
            {{ testimonial.author }}
            <span>{{ testimonial.date }}</span>
          </p>
        </div>
      </div>
        <div class="slider">
          <div v-for="(testimonial, index) in lastTestimonials()" :key="index">
            <div :class="currentIndex===index ? 'slider-point active' : 'slider-point'" @click="currentIndex=index"></div>
          </div>
        </div>
    </div>
    <div class="label" @click="nextSlide(lastTestimonials().length - 1)">
      <div class="next">
        <span>Next</span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SectionTestimonials',
  data() {
    return {
      currentIndex: 0,
    }
  },
  components: {},
  props: {
    testimonials: Array,
  },
  methods: {
    lastTestimonials() {
      if (this.testimonials.length > 3) {
        return this.testimonials.slice(
          this.testimonials.length - 3,
          this.testimonials.length,
        )
      } else {
        return this.testimonials
      }
    },
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
  computed: {
    computedCurrentIndex() {
      return this.currentIndex
    },
  },
}
</script>

<style scoped lang="scss">
@import '@/style/testimonials.scss';
</style>

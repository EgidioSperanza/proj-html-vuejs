<template>
  <div id="app">
    <header-app />
    <section-news :news="news" />
    <section-testimonials />
    <main-app />
    <footer-app />
  </div>
</template>

<script>
import HeaderApp from './components/HeaderApp.vue'
import SectionNews from './components/SectionNews.vue'
import SectionTestimonials from './components/SectionTestimonials.vue'
import MainApp from './components/MainApp.vue'
import FooterApp from './components/FooterApp.vue'

export default {
  name: 'App',
  components: {
    HeaderApp,
    SectionNews,
    SectionTestimonials,
    MainApp,
    FooterApp,
  },
  data() {
    return {
      news: ['no-image' ,'no-image','h3-img-1', 'h3-img-2', 'h3-img-3', 'h3-img-4'],
      testimonials: [
        {
          text:
            '"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua"',
          author: 'Washington post',
          date: 2018,
        },
        {
          text:
            '"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua"',
          author: 'Washington post',
          date: 2018,
        },

        {
          text:
            '"forget the trendy pizza shop, this hidden sspot makes the best new york-style pizza slice in naples"',
          author: 'Washington post',
          date: 2018,
        },
        {
          text:
            '"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua"',
          author: 'Washington post',
          date: 2018,
        },
        {
          text:
            '"forget the trendy pizza shop, this hidden sspot makes the best new york-style pizza slice in naples"',
          author: 'Washington post',
          date: 2018,
        },
      ],
    }
  },
}
</script>

<style lang="scss">
@import './style/main.scss';
</style>

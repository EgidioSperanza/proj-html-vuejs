<template>
  <div id="app">
    <header-app
      :jumboSlides="jumboSlides"
    />
    <section-news :news="news" />
    <section-testimonials :testimonials="testimonials" />
    <section-specials :specials="specials" />
    <section-custom-service />
    <footer-app />
  </div>
</template>

<script>
import HeaderApp from './components/HeaderApp.vue'
import SectionNews from './components/SectionNews.vue'
import SectionTestimonials from './components/SectionTestimonials.vue'
import SectionSpecials from './components/SectionSpecials.vue'
import SectionCustomService from './components/SectionCustomService.vue'
import FooterApp from './components/FooterApp.vue'

export default {
  name: 'App',
  components: {
    HeaderApp,
    SectionNews,
    SectionTestimonials,
    SectionSpecials,
    SectionCustomService,
    FooterApp,
  },
  data() {
    return {
      jumboSlides: [
        {
          textImgPath: 'h3-rev-img-1',
          pizzaImgPath: 'h3-rev-img-2',
        },
        {
          textImgPath: 'h3-rev-img-3',
          pizzaImgPath: 'h3-rev-img-4',
        },
        {
          textImgPath: 'h3-rev-img-5',
          pizzaImgPath: 'h3-rev-img-6',
        },
      ],
      news: [
        'no-image',
        'no-image',
        'h3-img-1',
        'h3-img-2',
        'h3-img-3',
        'h3-img-4',
      ],
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
          date: 2019,
        },
      ],
      specials:[
        {
          id:'fff27f37-b1a7-4e9e-8f7a-d237c64737ba',
          name:'Combo Piccolo',
          description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur imperdiet eros nisi, quis viverra lacus interdum sit amet.',
          price:'$10',
        },
        {
          id:'4055a68b-0a80-4ffb-94d5-8a8945be8358',
          name:'Combo mezzo',
          description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur imperdiet eros nisi, quis viverra lacus interdum sit amet.',
          price:'$20',
        },
        {
          id:'8c64e919-5fb3-4206-89c9-b7a72e91eb07',
          name:'Combo Grande',
          description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur imperdiet eros nisi, quis viverra lacus interdum sit amet.',
          price:'$30',
        },
      ],
    }
  },
  methods: {
  },
}
</script>

<style lang="scss">
@import './style/main.scss';
</style>

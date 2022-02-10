<template>
  <div id="app">
    <header-app :jumboSlides="jumboSlides" />
    <section-news :news="news" />
    <section-testimonials :testimonials="testimonials" />
    <section-specials :specials="specials" />
    <section-custom-service />
    <section-team :teamMembers="teamMembers" />
    <section-partners :partners="partners" />
    <section-pizza :pizzaMenu="pizzaMenu" />
    <section-events :events="events" />
    <section-booking />
    <footer-app
      :restaurantsLocations="restaurantsLocations"
      :societySocials="societySocials"
    />
  </div>
</template>

<script>
import HeaderApp from './components/HeaderApp.vue'
import SectionNews from './components/SectionNews.vue'
import SectionTestimonials from './components/SectionTestimonials.vue'
import SectionSpecials from './components/SectionSpecials.vue'
import SectionCustomService from './components/SectionCustomService.vue'
import SectionTeam from './components/SectionTeam.vue'
import SectionPartners from './components/SectionPartners.vue'
import SectionPizza from './components/SectionPizza.vue'
import SectionEvents from './components/SectionEvents.vue'
import SectionBooking from './components/SectionBooking.vue'
import FooterApp from './components/FooterApp.vue'

export default {
  name: 'App',
  components: {
    HeaderApp,
    SectionNews,
    SectionTestimonials,
    SectionSpecials,
    SectionCustomService,
    SectionTeam,
    SectionPartners,
    SectionPizza,
    SectionEvents,
    SectionBooking,
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
      specials: [
        {
          id: 'fff27f37-b1a7-4e9e-8f7a-d237c64737ba',
          name: 'Combo Piccolo',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur imperdiet eros nisi, quis viverra lacus interdum sit amet.',
          price: '$10',
        },
        {
          id: '4055a68b-0a80-4ffb-94d5-8a8945be8358',
          name: 'Combo mezzo',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur imperdiet eros nisi, quis viverra lacus interdum sit amet.',
          price: '$20',
        },
        {
          id: '8c64e919-5fb3-4206-89c9-b7a72e91eb07',
          name: 'Combo Grande',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur imperdiet eros nisi, quis viverra lacus interdum sit amet.',
          price: '$30',
        },
      ],
      teamMembers: [
        {
          id: 't6_4c',
          name: 'John Doe',
          picture: null,
          mansions: [null],
          socials: [
            { instagram: null, twitter: null, facebook: null, linkedin: null },
          ],
          vote_relevance: 0,
        },
        {
          id: 'w0z97',
          name: 'Jane Doe',
          picture: 'h1-team-2a',
          mansions: ['Pizza Chef'],
          socials: [
            {
              instagram: '/path',
              twitter: '/path',
              facebook: '/path',
              linkedin: null,
            },
          ],
          vote_relevance: 20,
        },
        {
          id: 'we-xy',
          name: 'John Doe',
          picture: 'h1-team-1a-700x700',
          mansions: ['Kitchen Porter', 'Pizza Chef'],
          socials: [
            {
              instagram: '/path',
              twitter: null,
              facebook: '/path',
              linkedin: '/path',
            },
          ],
          vote_relevance: 30,
        },
        {
          id: '8ioh9',
          name: 'Jane Doe',
          picture: 'h1-team-3a',
          mansions: ['Kitchen Porter'],
          socials: [
            {
              instagram: '/path',
              twitter: null,
              facebook: '/path',
              linkedin: null,
            },
          ],
          vote_relevance: 10,
        },
        {
          id: '1y20w',
          name: 'John Doe',
          picture: 'h1-team-4a',
          mansions: ['Photograph'],
          socials: [
            {
              instagram: '/path',
              twitter: '/path',
              facebook: '/path',
              linkedin: '/path',
            },
          ],
          vote_relevance: 10,
        },
      ],
      partners: [
        {
          name: 'Cowboy',
          logo: 'h1-clients-img-1',
        },
        {
          name: 'Gordon',
          logo: 'h1-clients-img-2',
        },
        {
          name: 'Big Cheese',
          logo: 'h1-clients-img-3',
        },
        {
          name: 'Bludoos Bar',
          logo: 'h1-clients-img-4',
        },
        {
          name: 'Vegan',
          logo: 'h1-clients-img-5',
        },
      ],
      pizzaMenu: [
        {
          name: 'Bismark',
          image: 'h3-product-img-1a-100x100',
          minPrice: '$30.00',
          maxPrice: null,
          labelSold: false,
        },
        {
          name: 'Fiori di Zucca',
          image: 'h3-product-img-2a-150x150',
          minPrice: '$7.00',
          maxPrice: '$50.00',
          labelSold: false,
        },
        {
          name: 'Valdostana',
          image: 'h3-product-img-3a-150x150',
          minPrice: '$55.00',
          maxPrice: null,
          labelSold: true,
        },
        {
          name: 'Pizza Tartufata',
          image: 'h3-product-img-4a-150x150',
          minPrice: '$45.00',
          maxPrice: null,
          labelSold: false,
        },
        {
          name: 'Francescana',
          image: 'h3-product-img-5a-150x150',
          minPrice: '$25.00',
          maxPrice: null,
          labelSold: false,
        },
        {
          name: 'Campagnola',
          image: 'h3-product-img-6a-100x100',
          minPrice: '$50.00',
          maxPrice: '95.00',
          labelSold: false,
        },
      ],
      events: [
        {
          event: 'traditional neapolitan pies in kyoto pizza mercato',
          location: '204 E. Pizzetta Tommaso',
          dateDay: '02',
          dateMonth: 'nov',
        },
        {
          event: 'terrazza patio dining space opening this weekend',
          location: '204 E. Pizzetta Tommaso',
          dateDay: '03',
          dateMonth: 'nov',
        },
        {
          event: 'sienna private dining room with stéphane brunn',
          location: '204 E. Pizzetta Tommaso',
          dateDay: '05',
          dateMonth: 'nov',
        },
      ],
      restaurantsLocations: [
        {
          address: '1614 E. Bell Rd #104.',
          city: 'Salerno, AZ 85022',
          telephone: '(602) 867-1010',
        },
        {
          address: '204 E. Pizzetta Tommaso',
          city: 'Sorrento, AZ 85022',
          telephone: '(358) 867-1010',
        },
        {
          address: 'Vale Puglia 54',
          city: 'Torre Del Greco, AZ 85022',
          telephone: '(359) 867-1010',
        },
        {
          address: 'Corso Itali AA',
          city: 'Naples, AZ 85022',
          telephone: '(989) 867-1010',
        },
        {
          address: '1614 E. Bell Rd #104.',
          city: 'Salerno, AZ 85022',
          telephone: '(602) 867-1010',
        },
        {
          address: '204 E. Pizzetta Tommaso',
          city: 'Sorrento, AZ 85022',
          telephone: '(358) 867-1010',
        },
        {
          address: 'Vale Puglia 54',
          city: 'Torre Del Greco, AZ 85022',
          telephone: '(359) 867-1010',
        },
        {
          address: 'Corso Itali AA',
          city: 'Naples, AZ 85022',
          telephone: '(989) 867-1010',
        },
      ],
      societySocials: [
        {
          twitter: '/path',
          facebook: '/path',
          instagram: '/path',
          linkedin: '/path',
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

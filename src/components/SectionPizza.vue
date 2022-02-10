<template>
  <section class="section-pizza">
    <h4>Choose your flavor</h4>
    <h1>the best pizza menu in town</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur asipiscing elit. Ut blandit arcu
      in pretium molestie. Interdum et malesuada fames ac.
    </p>
    <div class="slider-pizza">
      <div class="menu-pizza" :style="{ left: firstListPosition + 'px' }">
        <div
          class="pizza"
          v-for="(pizza, index) in pizzaMenu"
          :key="index"
          @mouseover="stopSlider()"
          @mouseleave="autoplaySliderMenu()"
        >
          <img :src="`/img/pizza/${pizza.image}.png`" :alt="pizza.name" />
          <div class="sold" v-if="pizza.labelSold">Sold</div>
          <h2>{{ pizza.name }}</h2>
          <p>
            {{ pizza.minPrice }}
            <span v-if="pizza.maxPrice">- {{ pizza.maxPrice }}</span>
          </p>
        </div>
      </div>
      <div class="menu-pizza" :style="{ left: secondListPosition + 'px' }">
        <div
          class="pizza"
          v-for="(pizza, index) in pizzaMenu"
          :key="index"
          @mouseover="stopSlider()"
          @mouseleave="autoplaySliderMenu()"
        >
          <div class="sold" v-if="pizza.labelSold">Sold</div>

          <img :src="`/img/pizza/${pizza.image}.png`" :alt="pizza.name" />
          <h2>{{ pizza.name }}</h2>
          <p>
            {{ pizza.minPrice }}
            <span v-if="pizza.maxPrice">- {{ pizza.maxPrice }}</span>
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SectionPizza',
  data() {
    return {
      intervalId: '',
      menuPizzaWidth: this.pizzaMenu.length * 450, //width+margin
      firstListPosition: 0, //left
      secondListPosition: this.pizzaMenu.length * 450, //left
    }
  },
  props: {
    pizzaMenu: Array,
  },
  methods: {
    autoplaySliderMenu() {
      if (!this.intervalId) {
        this.intervalId = setInterval(this.sliderMotion, 1)
      }
    },
    sliderMotion() {
      if (this.firstListPosition > this.menuPizzaWidth * -1) {
        this.firstListPosition--
      } else {
        this.firstListPosition = this.menuPizzaWidth
      }
      if (this.secondListPosition > this.menuPizzaWidth * -1) {
        this.secondListPosition--
      } else {
        this.secondListPosition = this.menuPizzaWidth
      }
    },

    stopSlider() {
      clearInterval(this.intervalId)
      this.intervalId = null
    },
  },
  mounted() {
    this.autoplaySliderMenu()
  },
  computed: {
    computedFirstPosition() {
      return this.firstListPosition
    },
    computedSecondPosition() {
      return this.SecondListPosition
    },
  },
}
</script>

<style scoped lang="scss">
@import '@/style/pizza.scss';
</style>

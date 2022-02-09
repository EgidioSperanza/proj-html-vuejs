<template>
  <section class="section-pizza">
    <h4>Choose your flavor</h4>
    <h1>the best pizza menu in town</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur asipiscing elit. Ut blandit arcu
      in pretium molestie. Interdum et malesuada fames ac.
    </p>
    <div class="slider-pizza">
      <div class="menu-pizza" :style="{ left: firstListPosition + 'px' }" @mouseover="stopSlider()" @mouseleave="autoplaySliderMenu()">
        <div class="pizza" v-for="(pizza, index) in pizzaMenu" :key="index">
          <img :src="`/img/pizza/${pizza.image}.png`" :alt="pizza.name" />
          <div class="sold" v-if="pizza.labelSold">Sold</div>
          <h2>{{ pizza.name }}</h2>
          <p>
            {{ pizza.minPrice }}
            <span v-if="pizza.maxPrice">- {{ pizza.maxPrice }}</span>
          </p>
        </div>
      </div>
      <div class="menu-pizza" :style="{ left: secondListPosition + 'px' }" @mouseover="stopSlider()" @mouseleave="autoplaySliderMenu()">
        <div class="pizza" v-for="(pizza, index) in pizzaMenu" :key="index">
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
      menuPizzaWidth: this.pizzaMenu.length * 400, //width+margin
      firstListPosition: 0, //left
      secondListPosition: this.pizzaMenu.length * 400, //left
    }
  },
  props: {
    pizzaMenu: Array,
  },
  methods: {
    autoplaySliderMenu() {
      if (!this.intervalId) {
        this.intervalId = setInterval(this.sliderMotion, 0.1)
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
@import '@/style/variables.scss';

.section-pizza {
  width: 100%;
  height: 700px;
  padding: 100px 0;
  display: flex;
  flex-direction: column;
  align-items: center;

  h4,
  h1 {
    text-transform: uppercase;
  }
  h4 {
    color: $text-orange-red;
    margin-bottom: 5px;
  }
  h1 {
    margin-bottom: 10px;
  }
  p {
    width: 500px;
    color: $text-gray;
    text-align: center;
    line-height: 25px;
    padding-bottom: 100px;
  }
  .slider-pizza {
    position: relative;
    width: 100%;
    .menu-pizza {
      width: 100%;
      display: flex;
      padding-bottom: 200px;
      position: absolute;
      .pizza {
        width: 200px;
        margin: 0 100px;
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;
        &:hover{
          transform: scale(1.2);
        }
        h2{
          color:$text-gold;
        }
        p{
          color:$text-orange-red;
          font-weight: 900;
        }
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
        .sold {
          position: absolute;
          top: 20px;
          right: 0;
          width: 60px;
          height: 60px;
          border-radius: 100%;
          background-color: $bkg-orange-red;
          color:$text-no-pure-white;
          text-transform: uppercase;
          text-align: center;
          line-height: 60px;
          font-size: 12px;
        }
      }
    }
  }
}
</style>

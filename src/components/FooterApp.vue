<template>
  <footer>
    <div class="footer-info">
      <div class="restaurants-location">
        <h3>Find our Restaurants</h3>
        <div
          class="restaurant"
          v-for="(restaurant, index) in filteredLocations()"
          :key="index"
        >
          <p>{{ restaurant.address }}</p>
          <p>{{ restaurant.city }}</p>
          <p>{{ restaurant.telephone }}</p>
        </div>
      </div>
      <div class="working-hours">
        <h3>Working Hours</h3>
        <h5>monday</h5>
        <p class="closed">Kitchen Closed</p>
        <h5>tuesday until friday</h5>
        <p>9:00 - 22:00</p>
        <h5>
          saturday
          <span>*</span>
        </h5>
        <p>Saturday 11am to midnight</p>
        <h5>Sunday</h5>
        <p>9:00 - 22:00</p>
        <div class="socials">
          <h5>follow us:</h5>
          <div v-for="(social, index) in societySocials" :key="index">
            <span v-if="social.twitter !== null">
              <a :href="social.twitter"><i class="fab fa-twitter"></i></a>
            </span>
            <span v-if="social.facebook !== null">
              <a :href="social.facebook"><i class="fab fa-facebook"></i></a>
            </span>
            <span v-if="social.instagram !== null">
              <a :href="social.instagram"><i class="fab fa-instagram"></i></a>
            </span>
            <span v-if="social.linkedin !== null">
              <a :href="social.linkedin"><i class="fab fa-linkedin"></i></a>
            </span>
          </div>
        </div>
      </div>
      <div class="cause">
        the don peppe crew first and foremost values an authentic, well baked
        slice of pizza.
      </div>
      <span class="created">Created whit <i class="fas fa-heart"></i> by <span>SpiderDevWeb</span></span>
    </div>
    <div class="footer-image"></div>
  </footer>
</template>

<script>
export default {
  name: 'FooterApp',
  props: {
    restaurantsLocations: Array,
    societySocials: Array,
  },
  methods: {
    filteredLocations() {
      if (this.restaurantsLocations.length > 4) {
        return this.restaurantsLocations.slice(0, 4)
      } else {
        return this.restaurantsLocations
      }
    },
  },
}
</script>

<style scoped lang="scss">
@import '@/style/header.scss';

footer {
  width: 100%;
  background-color: $bkg-dark;
  display: flex;
  min-height: 700px;

  .footer-info {
    position: relative;
    width: 50%;
    padding: 100px 50px 100px 30px;
    display: flex;
    justify-content: space-between;

    .cause {
      text-transform: uppercase;
      font-size: 25px;
      width: 300px;
      color: $text-white;
      margin-left: 50px;
    }
  }
  .footer-image {
    width: 50%;
    background: url('/img/pixel-bkg/footer-img-1.jpg') no-repeat;
    background-size: cover;
  }
}
h3,
h5 {
  color: $text-gold;
}
h3 {
  padding-bottom: 20px;
}
h5 > span,
.closed {
  color: $text-orange-red;
}
p {
  color: $text-gray;
}
.restaurant :last-child{
  margin-bottom: 20px;
}
.working-hours p {
  padding-bottom: 20px;
}
.socials {
  display: flex;
  margin-top: 40px;
}
.socials span {
  margin: 0 5px;
}
.created{
  position: absolute;
  bottom: 10px;
  color: $text-gold;

  span{
    color: #339966;
  }
}
</style>

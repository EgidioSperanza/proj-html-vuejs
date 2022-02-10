<template>
  <section class="section-booking">
    <div class="booking">
      <div class="persons">
        <input id="persons" name="person" type="text" placeholder="1 Person" />
        <i class="fas fa-user-friends"></i>
      </div>
      <span>FOR</span>
      <div class="date">
        <input
          id="date"
          name="date"
          type="text"
          :placeholder="getHumanDate(new Date())"
        />
        <i class="fas fa-calendar-alt"></i>
      </div>
      <span>AT</span>
      <div class="time">
        <input id="time" name="time" type="text" :placeholder="`7:00 pm`" />
        <i class="fas fa-clock"></i>
      </div>
      <button>BOOK A TABLE</button>
      <span class="powered">*Powered by SpiderDev</span>
    </div>
  </section>
</template>

<script>
import moment from 'moment'
export default {
  name: 'SectionBooking',
  data() {
    return {}
  },
  methods: {
    getHumanDate: function (date) {
      return moment(date, 'YYYY-MM-DD').format('DD/MM/YYYY')
    },
  },
}
</script>

<style scoped lang="scss">
@import '@/style/variables.scss';
.section-booking {
  background: url('/img/pixel-bkg/h3-background-img-3.jpg') no-repeat;
  background-size: cover;
  margin-bottom: 10px;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;

  .booking {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;

    span:not(.powered) {
      width: 60px;
      text-align: center;
      color: $text-white;
    }
    .persons,
    .date,
    .time {
      position: relative;
    }
    i {
      position: absolute;
      top: 20px;
      right: 20px;
      color: $text-gold;
      font-size: 20px;
    }
    input {
      height: 60px;
      width: 240px;
      padding-left: 20px;
      border: 2px solid $input-border;
    }
    button {
      margin-left: 60px;
    }
  }
  .powered {
    position: absolute;
    bottom: -30px;
    left: 0;
    color: $text-white;
  }
}
</style>

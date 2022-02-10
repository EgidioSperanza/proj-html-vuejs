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
@import '@/style/booking.scss';
</style>

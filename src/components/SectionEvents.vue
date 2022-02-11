<template>
  <section class="events-section" id="events">
    <div class="events">
      <h5>made with love</h5>
      <h1>delish pizza deals</h1>
      <div
        v-for="(event, index) in events"
        :key="index"
        :class="index !== events.length - 1 ? 'event bordered' : 'event'"
      >
        <div class="date">
          <span class="date-day">
            {{ event.dateDay }}
          </span>
          <span class="date-month">{{ event.dateMonth }}</span>
        </div>
        <div class="event-info">
          <h2>{{ event.event }}</h2>
          <p><i class="fas fa-map-marker-alt"></i> {{ event.location }}</p>
        </div>
      </div>
    </div>
    <div class="advertising-events"></div>
  </section>
</template>

<script>
export default {
  name: 'SectionEvents',
  props: {
    events: Array,
  },
  methods: {},
}
</script>

<style scoped lang="scss">
@import '@/style/events.scss';
</style>

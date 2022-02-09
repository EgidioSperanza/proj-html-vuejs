<template>
  <section class="specials-section">
    <div class="advertising-image">
      <img src="/img/specials/h1-img-7n.png" alt="Pizza Specials Logo" />
    </div>
    <div class="specials-menu">
      <div class="specials-list">
        <h1>Specials*</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur
          imperdiet eros nisi, quis viverra lacus interdum sit amet.
        </p>
        <div
          class="special-element"
          v-for="special in specials"
          :key="special.id"
        >
          <span>{{ special.price }}</span>
          <div class="special-info">
            <h2>{{ special.name }}</h2>
            <p>{{ special.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SectionSpecials',
  props: {
    specials: Array,
  },
  methods: {},
}
</script>

<style scoped lang="scss">
@import '@/style/specials.scss';
</style>

<template>
  <section class="section-partners">
    <div class="partners">
      <div
        class="partner"
        v-for="(partner, index) in filteredPartners()"
        :key="index"
      >
        <img
          :src="`/img/partners/${partner.logo}.png`"
          :alt="`Logo ${partner.name}`"
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SectionPartners',
  data() {
    return {}
  },
  props: {
    partners: Array,
  },
  methods: {
    filteredPartners() {
      if (this.partners.length > 5) {
        let randomPartners = []
        let random = 0
        for (let i = 0; i <= 3; i++) {
          random = Math.floor(Math.random() * this.partners.length)
          console.log(random)
          if (randomPartners.includes(this.partners[random])) {
            i--
          } else {
            randomPartners.push(this.partners[random])
          }
        }
        console.log(randomPartners)
        return randomPartners
      } else {
        return this.partners
      }
    },
  },
}
</script>

<style scoped lang="scss">
@import '@/style/variables.scss';
.section-partners {
  width: 100%;
  background-color: $bkg-no-pure-white;
  padding: 100px 0;
  margin-bottom: 10px;
  .partners {
    margin: 0 auto;
    width: $container-width;
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
</style>

<template>
  <section class="news-section">
    <!-- LAST 4 ELEMENTS OF NEWS ARRAY-->
    <div class="news" v-for="(announcement, index) in lastNews()" :key="index">
      <div class="new">
        <div class="new-info"><i class="fas fa-eye"></i></div>
        <img
          :src="`/img/news/${announcement}.jpg`"
          alt="Don Peppe Pizza News"
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SectionNews',
  props: {
    news: Array,
  },
  methods: {
    lastNews() {
      if (this.news.length > 4) {
        return this.news.slice(this.news.length - 4, this.news.length)
      } else {
        return this.news
      }
    },
  },
}
</script>

<style scoped lang="scss">
@import '@/style/news.scss';

</style>

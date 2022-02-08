<template>
  <section class="news-section">
    <!-- LAST 4 ELEMENTS OF NEWS ARRAY-->
    <div class="news" v-for="(announcement, index) in lastNews()" :key="index">
      <div class="new">
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
    lastNews(){
     return this.news.slice(this.news.length-4, this.news.length)
    }
  },
}
</script>

<style scoped lang="scss">
@import '@/style/variables.scss';
.news-section {
  width: 100%;
  margin: 10px 0;
  display: flex;
  justify-content: space-between;
  .news{
    width: calc((100% / 4) - (30px / 4));
  }
    img {
      width: 100%;
    }
}
</style>

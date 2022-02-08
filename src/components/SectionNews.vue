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
@import '@/style/variables.scss';
.news-section {
  width: 100%;
  margin: 10px 0;
  display: flex;
  justify-content: space-between;

  .news {
    width: calc((100% / 4) - (30px / 4));
    display: flex;
    justify-content: center;
    align-items: center;
    &:hover {
      background: url('/img/pixel-bkg/bkg-pixel-news.png');
    }
    &:hover img {
      display: none;
    }
    &:hover .new-info {
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .new-info {
      display: none;
      width: 80px;
      height: 80px;
      font-size: 30px;
      color: $text-white;
      background-color: $bkg-orange-red;
      border-radius: 100%;
      cursor: pointer;
    }
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}
</style>

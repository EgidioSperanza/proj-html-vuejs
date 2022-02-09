<template>
  <section class="section-custom">
    <div class="top-left"></div>
    <div class="top"></div>
    <div class="top-right"></div>
    <div class="left"></div>
    <div class="main">
      <div class="advertise-service"><h1>Go Ahead and build your pizza we won't judge!</h1></div>
    </div>
    <div class="right"></div>
    <div class="bottom-left"></div>
    <div class="bottom"></div>
    <div class="bottom-right"></div>
  </section>
</template>

<script>
export default {
  name: 'SectionCustomService',
  props: {},
  methods: {},
}
</script>

<style scoped lang="scss">
@import '@/style/variables.scss';
.section-custom {
  width: 100%;
  margin-bottom: 10px;
  display: flex;
  flex-wrap: wrap;
  .top {
    width: calc(100% - 200px);
    height: 100px;
    background: url('/img/h3-background-img.jpg') bottom;
    background-size: cover;
  }
  .top-right {
    width: 100px;
    height: 100px;
    background: url('/img/h3-background-img.jpg');
  }
  .right {
    width: 100px;
    background: url('/img/h3-background-img.jpg') 10% 0;
  }
  .bottom-right {
    width: 100px;
    height: 100px;
    background: url('/img/h3-background-img.jpg') 20% 20%;
  }
  .bottom {
    width: calc(100% - 200px);
    height: 100px;
    background: url('/img/h3-background-img.jpg') 0 60%;
    background-size: cover;
  }
  .bottom-left {
    width: 100px;
    height: 100px;
    background: url('/img/h3-background-img.jpg') 100% 60%;
  }
  .left {
    width: 100px;
    background: url('/img/h3-background-img.jpg') 100% 0;
  }
  .top-left {
    width: 100px;
    height: 100px;
    background: url('/img/h3-background-img.jpg') 100% 100%;
  }
  .main {
    width: calc(100% - 200px);
    height: 300px;
    background: url('/img/h3-background-img.jpg');
    background-size: cover;
    position: relative;

    .advertise-service{
      width: 350px;
      height: 340px;
      top:0;
      left:0;
      margin-top:-20px;
      margin-left: 20%;
      text-transform: uppercase;
      font-size: 38px;
      color: $text-no-pure-white;
    }
  }
}
</style>

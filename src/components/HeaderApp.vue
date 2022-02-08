<template>
  <header>
    <div class="navbar">
      <div>
        <button>Order Online</button>
      </div>
      <nav>
        <div class="menu-left">
          <ul>
            <li>Home</li>
            <li>Pages</li>
            <li>Menu</li>
          </ul>
        </div>
        <div class="logo">
          <img
            src="/img/logo/h5-logo-divided-header.png"
            alt="Don Peppe Logo"
          />
        </div>
        <div class="menu-right">
          <ul>
            <li>Event</li>
            <li>Blog</li>
            <li>Landing</li>
          </ul>
        </div>
      </nav>
      <div class="navbar-right">
        <ul>
          <li>cart</li>
          <li>search</li>
        </ul>
      </div>
    </div>
    <div class="jumbotron">
      <div class="label prev"></div>
      <div class="jumbo-focus"><img src="/img/jumbotron/h3-rev-img-2.png" alt="" /></div>
      <div class="label next"></div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderApp',
  props: {},
}
</script>

<style scoped lang="scss">
@import '@/style/header.scss';
</style>

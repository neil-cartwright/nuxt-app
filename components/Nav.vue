<template>
  <nav class="navbar is-light" role="navigation" aria-label="main navigation">
    <div class="container is-max-desktop">
      <div class="navbar-brand">
        <a class="navbar-item title is-size-6" href="/">
          Our dvd collection
        </a>
        <!-- <div
          class="navbar-burger"
          :class="{ 'is-active': openNav }"
          @click="openNav = !openNav"
        >
          <span />
          <span />
          <span />
        </div> -->
      </div>
      <div class="navbar-menu" :class="{ 'is-active': openNav }">
        <div class="navbar-left"></div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      openNav: false
    };
  }
};
</script>

<style lang="scss" scoped>
.nuxt-link-exact-active {
  color: black;
}
@media screen and (min-width: 1024px) {
  .navbar-menu {
    display: flex;
    justify-content: space-between;
  }
  .navbar-menu .navbar-left,
  .navbar-menu .navbar-right {
    display: flex;
  }
}
</style>

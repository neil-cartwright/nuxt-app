<template>
  <div class="is-flex is-flex-direction-column flex-wrapper">
    <Nav />
    <Hero />
    <section class="main-content columns is-flex-grow-1">
      <div class="container column is-10">
        <nuxt />
      </div>
    </section>
    <footer class="footer has-background-light">
      <p>Footer</p>
    </footer>
  </div>
</template>

<script>
import Nav from "~/components/Nav";
import Hero from "~/components/Hero";
export default {
  components: {
    Nav
  },
  data() {
    return {
      items: [
        {
          title: "Home",
          icon: "home",
          to: { name: "index" }
        },
        {
          title: "Inspire",
          icon: "lightbulb",
          to: { name: "inspire" }
        }
      ]
    };
  }
};
</script>

<style>
.flex-wrapper {
  min-height: 100vh;
}
</style>

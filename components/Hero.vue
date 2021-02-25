<template>
  <div class="hero">
    <div class="hero-body"></div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.hero {
  background: url("~assets/images/dvd-store.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  min-height: 300px;
}
.hero-body {
  display: flex;
  align-items: center;
  justify-content: center;
}
h1 {
  opacity: 0.9;
  padding: 1rem;
}
</style>

<template>
  <div class="column" :class="'is-' + width">
    <slot></slot>
  </div>
</template>
<script>
export default {
  props: ["width"]
};
</script>

<style lang="scss" scoped></style>

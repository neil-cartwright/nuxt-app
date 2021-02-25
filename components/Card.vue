<template>
  <div class="card">
    <div class="card-header">
      <div class="card-header-title">//title post</div>
    </div>
    <div class="card-image">
      <figure class="is-image is-128x128">
        <img :src="require(`~/assets/images/${img}.jpg`)" alt="landscape" />
      </figure>
    </div>
    <div class="card-content">
      // card content
    </div>
    <div class="card-footer">
      <div class="card-footer-item">//footer item</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    img: {
      type: String,
      required: true
    }
  }
};
</script>

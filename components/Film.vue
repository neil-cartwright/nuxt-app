<template>
  <div class="column is-12">
    <div class="film">
      <div class="film__title">
        <div class="">
          <span>{{ film.title }}</span>
        </div>
        <div class="film__year">
          <a @click="sendSelectedInput">{{ film.year }}</a>
        </div>
      </div>

      <div class="film__talent">
        <div class="film__director">
          <a @click="sendSelectedInput">{{ film.director }}</a>
        </div>

        <div class="film__stars">
          <a @click="sendSelectedInput">{{ film.leading_actor }}</a>
          <a @click="sendSelectedInput">{{ film.supporting_actor }}</a>
        </div>
      </div>

      <div class="film__genres">
        <span v-for="(g, idx) in film.genres.split(' ')" class="" :key="idx"
          ><a @click="sendSelectedInput">{{ g }}</a></span
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["film"],
  data() {
    return {
      selectedInput: ""
    };
  },
  methods: {
    sendSelectedInput: function(event) {
      this.selectedInput = event.target.textContent;
      this.$emit("send-selected", this.selectedInput);
    }
  }
};
</script>

<style lang="scss" scoped>
// * {
//   outline: 1px solid red;
// }
.film {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  border-radius: 0.25rem;
  border: 1px solid #e8e8e8;

  a {
    color: inherit;
    &:hover {
      opacity: 0.9;
      text-decoration: underline;
    }
  }

  .film__title {
    font-weight: 700;
    font-size: 1.2rem;
    text-transform: capitalize;
    width: 100%;
    display: flex;
    align-items: flex-end;
    background: #e8e8e8;
    padding: 0.5rem;

    .film__year {
      font-weight: 300;
      margin-left: 0.5rem;
      font-size: 0.95rem;
    }
  }

  .film__talent {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    flex-direction: column;
    flex: 0 1 auto;
    padding: 0.5rem;

    .film__director {
      font-weight: 700;
      margin-right: 1rem;
    }

    .film__stars {
      font-style: italic;
      display: flex;
      justify-content: space-between;

      a:first-child {
        margin-right: 0.5rem;
      }
    }
  }
  .film__genres {
    display: flex;
    align-items: center;
    padding: 0.5rem;
    span {
      margin-right: 0.5rem;
      font-size: 0.9rem;
    }
  }

  .film__genres span:not(:last-child)::after {
    content: " - ";
  }
}
</style>

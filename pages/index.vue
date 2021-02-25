<template>
  <div>
    <div class="container is-max-desktop">
      <section class="section">
        <div class="box">
          <div class="field is-grouped">
            <div class="control">
              <input type="text" class="input" v-model="input" />
            </div>
            <button class="button" type="button" @click="input = ''">
              All
            </button>
          </div>
        </div>
        <div class="columns is-multiline">
          <Film
            v-for="(f, idx) in filteredFilms"
            :key="idx"
            :film="f"
            @send-selected="searchForSelected"
          />
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import Film from "@/components/Film";
import axios from "axios";
export default {
  name: "Index",
  head() {
    return {
      title: "DVD Collection"
    };
  },
  transition: "home",
  data() {
    return {
      films: [],
      filmsArray: [],
      input: ""
    };
  },
  watch: {
    tempArr: function() {
      console.log(this.tempArr);
    }
  },
  computed: {
    filteredFilms() {
      return this.filterByValue(this.films, this.input);
    }
  },
  methods: {
    filterByValue: function(array, string) {
      return array.filter(
        data =>
          JSON.stringify(data)
            .toLowerCase()
            .indexOf(string.toLowerCase()) !== -1
      );
    },
    fetchFilmsFromAPI() {
      axios
        .get("https://films.sitepages.co.uk/api/all")
        .then(res => {
          this.filmsArray = res.data;
          this.loopFilmsArray(this.filmsArray);
        })
        .catch(error => {
          console.log(error);
        });
    },
    loopFilmsArray: function(a) {
      for (let i = 0; i < a.length; i++) {
        this.films.push(a[i]);
      }
    },
    searchForSelected: function(selected) {
      this.input = selected;
    }
  },
  created() {
    this.fetchFilmsFromAPI();
  }
};
</script>
<style>
.home-enter-active,
.home-leave-active {
  transition: opacity 0.5s;
}
.home-enter,
.home-leave-active {
  opacity: 0;
}
</style>

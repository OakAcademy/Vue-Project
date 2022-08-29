<template>
  <div>
    <SearchInput @newTerm="handleNewTerm"></SearchInput>
    <Videos v-bind:videos="videos"></Videos>
  </div>
</template>

<script>
import SearchInput from "./components/SearchInput.vue";
import Videos from "./components/Videos.vue";
const API_KEY = "24513570-73f91d28485582e52dec2030c";

export default {
  name: "App",
  components: {
    SearchInput,
    Videos,
  },
  data() {
    return {
      videos: [],
    };
  },
  methods: {
    async handleNewTerm(searchInput) {
      const response = await fetch(
        "https://pixabay.com/api/videos/?" +
          new URLSearchParams({
            key: API_KEY,
            q: searchInput,
          })
      );
      const data = await response.json();
      this.videos = data.hits;
      console.log(this.videos);
      // this.totalVuePackages = data.total;
    },
  },
};
</script>

<style>
</style>

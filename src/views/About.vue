<template>
  <div class="about">
      <div v-for="about in abouts" :key="about.index">
        <h1>{{ about.title }}</h1>
        <img :src="about.image" :alt="about.slug">
        <p>{{ about.text }}</p>
      </div>
  </div>
</template>


<script>
import axios from 'axios';
export default {
  data() {
    return {
      abouts: [],
    }
  },
  created() {
    axios.get(`https://kolitech-site.dev/wp-json/kolitech/v1/about`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.abouts = response.data;
    });
  }
}
</script>

<style lang="scss" scoped>
  img {
    width: 150px;
    height: 150px;
    border-radius: 50%;
  }
</style>

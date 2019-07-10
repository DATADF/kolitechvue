<template>
  <div id="articles">
    <div v-for="(article, index) in articles" :key="index">
      <h1>{{ article.title }}</h1>
      <h3>{{ article.category }}</h3>
      <img :src="article.image" :alt="article.slug">
      <p>{{ article.resumo }}</p>
    </div>
  </div>
</template>


<script>

import axios from 'axios';

export default {
  data() {
    return {
      articles: [],
    }
  },

  // Fetches posts when the component is created.
  created() {
    axios.get(`https://kolitech-site.dev/wp-json/kolitech/v1/articles`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.articles = response.data;
    });
  }
}
</script>

<style lang="scss" scoped>
  img {
    width: 20%;
    height: auto;
  }
</style>
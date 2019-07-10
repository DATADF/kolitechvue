<template>
  <div id="services">
    <div v-for="(service, index) in services" :key="index">
      <h1>{{ service.title }}</h1>
      <h3>{{ service.category }}</h3>
      <img :src="service.image" :alt="service.slug">
      <p>{{ service.resumo }}</p>
    </div>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  data() {
    return {
      services: [],
    }
  },

  // Fetches posts when the component is created.
  created() {
    axios.get(`https://kolitech-site.dev/wp-json/kolitech/v1/services`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.services = response.data;
    });
  }
}

</script>

<style lang="scss" scoped>

.container {
  width: 90%;
  max-width: 960px;
  margin: 0 auto;
}

  img {
    width: 20%;
    height: auto;
  }

</style>
<template>
  <div class="contact">
    <div v-for="mensagem in mensagens" :key="mensagem.index">
      <h1>{{ mensagem.title }}</h1>
      <button @click="mensagem.id">Ver</button>
    </div>
  </div>
</template>

<script>

import axios from 'axios';
import { METHODS } from 'http';
export default {
  data() {
    return {
      mensagens: [],
    }
  },
  created() {
    axios.get(`https://kolitech-site.dev/wp-json/kolitech/v1/services`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.mensagens = response.data;
    });
  }
  
}
</script>

<style lang="scss" scoped>

</style>

<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti facere distinctio non veniam, dolore atque aliquid, ut magnam eligendi, consectetur iure asperiores neque iusto. Ipsum dignissimos earum amet rerum nemo?</p>
  </div>
</template>

<script>
export default {
  name: 'index',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

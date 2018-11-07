<template>
  <div id="app">
    <app-make-post
    v-bind:title="title"></app-make-post>
  </div>
</template>

<script>
import MakeBlogPost from './Components/Make-blog-post';

export default {

  components: {
    'app-make-post': MakeBlogPost
  },

  data () {
    return {
      title: "Hello, welcome to the Vuejs blog!"
    }
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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

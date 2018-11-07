<template>
  <b-container >
    <b-col id="col">
      <b-row>
          <h1>{{ title }}</h1>
      </b-row>
      <b-row>
          <h3>Blog title: <input
            type="text"
            name=""
            value=""
            v-model="blogTitle"></h3>
        </b-row>
      <b-row>
          <textarea
          rows="10"
          cols="70"
          placeholder="Write you blog in here..."
          v-model="blogConentent"></textarea>
        </b-row>
      <b-row>
        <button
        type="button"
        name="button"
        class="btn btn-success"
        v-on:click="createNewPost(blogTitle)">Create</button>
        <p v-if="showPost">{{ newPosts }}</p>
      </b-row>
    </b-col>
  </b-container>
</template>

<script>
// onClick => show post => reset button => onClick=> create new blogPost
export default {
  props: [
    'title'
  ],
  data () {
    return {
      showPost: false,
      blogTitle: "",
      blogConentent: "",
      newPosts: []
    }
  },
  methods: {
    createNewPost: function(blogTitle){
      this.showPost = true;
      this.newPosts.push(blogTitle);
      console.log(this.newPosts);
      this.blogTitle = "";
    }
  }
}

</script>

<style scoped>
.container {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0 auto;
}

h1, h2 {
  font-weight: normal;
  font-size: 50px;
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

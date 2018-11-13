<template>
  <b-container id="container">
      <b-col>
        <form class="" action="index.html" method="post" v-if="!hideBlogMaker">
        <b-row>
            <h1 id="title" class="center">{{ title }}</h1>
        </b-row>
        <b-row>
            <h3 id="blog-title" class="center">Blog title: <input
              type="text"
              name=""
              value=""
              v-model.lazy="postObj.blogTitle"></h3>
          </b-row>
        <b-row>
            <textarea
            class="center"
            rows="5"
            cols="50"
            placeholder="Write you blog in here..."
            v-model.lazy="postObj.blogContent"></textarea>
          </b-row>
        <b-row>
          <div id="post-category">
            <label for="">Post Category</label>
            <select v-model="postObj.category">
                <option value="Sports">Sports</option>
                <option value="Food">Food</option>
                <option value="Climate">Climate</option>
            </select>
          </div>
        </b-row>
      </form>
        <b-row>
          <div id="innerPost">
            <h3>Title: {{ postObj.blogTitle }}</h3>
            <p>Blog content: {{ postObj.blogContent }}</p>
            <p> Category: {{ postObj.category }} </p>
            <button
            type="button"
            name="button"
            class="btn btn-info"
            v-on:click="createBlogPost"
            v-if="!hideBlogMaker">Create</button>
            <button
            class="btn btn-info"
            type="button"
            name="button"
            v-if="hideBlogMaker"
            v-on:click="showBlogMaker">New Post</button>
          </div>
        </b-row>
      </b-col>
  </b-container>
</template>

<script>

export default {
  props: [
    'title'
  ],
  data () {
    return {
      showPost: false,
      postObj: {
        blogTitle: "",
        blogContent: "",
        category: ""
      },
      hideBlogMaker: false
    }
  },
  methods: {
    createBlogPost: function(){
      this.hideBlogMaker = true;
    },
    showBlogMaker: function(){
      this.hideBlogMaker = false;
    }
  }
}

</script>

<style scoped>
#container {
  margin: 0 auto;
  background-color: #e2e2e2;
}
#title{

}
#blog-title{
  box-sizing: border-box;
  width: 100%;
  padding: 5px;
}
.center{
  margin: 0 auto;
  text-align: center;
}
#post-category{
  margin: 0 auto;
  text-align: center;
}
#newPost{
  margin: 0 auto;
  padding: 50px;
  text-align: center;
  font-size: 40px;
}
#postContainer{
}
h1, h2 {
  font-weight: normal;
  font-size: 50px;
}
#innerPost{
  margin: 20px auto;
  padding: 10px 150px;
  background-color: #e5f0f9;
}
a {
  color: #42b983;
}
</style>

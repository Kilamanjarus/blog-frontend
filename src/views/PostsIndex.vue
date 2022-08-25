<script>
import axios from 'axios';

export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      posts: {},

    };
  },
  created: function () {
    this.postsIndex();
  },
  methods: {
    postsIndex: function () {
      console.log(`Pulling Blogs`)
      axios.get("http://localhost:3000/posts").then(response => {
        console.log(response.data)
        this.posts = response.data
      })
    }
  },
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="post in posts">
      <p><a v-bind:href="`/posts/${post.id}`">{{ post.title }}</a></p>
      <p>{{ post }}</p>
    </div>
  </div>
</template>

<style>
</style>
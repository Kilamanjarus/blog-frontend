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
        console.log(`response.data`)
        this.posts = response.data
      })
    }
  },
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <p v-for="post in posts">
      {{ post }}
    </p>
  </div>
</template>

<style>
</style>
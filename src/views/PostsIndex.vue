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
    <h1>{{  message  }}</h1>
    <div>
      <div class="row">
        <div class="col-sm-6" v-for="post in posts">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">{{  post.title  }}</h5>
              <p class="card-text">{{  post.body  }}</p>
              <a v-bind:href="`/posts/${post.id}`" class="btn btn-primary">Show More!</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<style>
</style>
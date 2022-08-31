<script>
import axios from 'axios';

export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      post: {}
    };
  },
  created: function () {
    this.postsShow();
  },
  methods: {
    postsShow: function () {
      console.log(`Showing post...`)
      console.log(this.$route.params.id)
      axios.get(`/posts/${this.$route.params.id}.json`).then(response => {
        console.log(response.data)
        this.post = response.data
      })
    }
  }
};
</script>

<template>
  <div class="home">
    <h1>{{ post }}</h1>
    <br />
    <a v-if="post.owner === true" v-bind:href="`/posts/${post.id}/edit`">Edit</a>
  </div>
</template>

<style>
</style>
<script>
import axios from 'axios';

export default {
  data: function () {
    return {
      message: "Welcome to Editting.",
      post: {}
    };
  },
  created: function () {
    this.postsShow();
  },
  methods: {
    postsShow: function () {
      console.log(`Showing post in edit...`)
      console.log(this.$route.params.id)
      axios.get(`/posts/${this.$route.params.id}.json`).then(response => {
        console.log(response.data)
        this.post = response.data
      })
    },
    postUpdate: function () {
      console.log(`Editing post...`)
      axios.patch(`/posts/${this.$route.params.id}.json`, this.post).then(response => {
        console.log(response.data)
        this.$router.push(`/posts/${this.post.id}`);
      })
    },
    postDelete: function () {
      console.log(`Deleting post....`)
      axios.delete(`/posts/${this.$route.params.id}.json`).then(response => {
        console.log(response.data)
        this.$router.push("/posts")
      })
    }
  },
};
</script>

<template>
  <div class="posts-edit">
    {{  message  }}
    <button @click="postDelete()">Delete</button>
    <h1>{{  post.id  }}</h1>
    <p>Title: <input type="text" v-model="post.title" /></p>
    <p>User Id: <input type="text" v-model="post.user_id" /></p>
    <p>Body: <input type="text" v-model="post.body" /></p>
    <p>Image Url: <input type="text" v-model="post.image" /></p>
    <button v-on:click="postUpdate()">Update</button>

  </div>
</template>

<style>
</style>

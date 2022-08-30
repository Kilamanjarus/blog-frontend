<script>
import axios from 'axios';

export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      newPostParams: {},
      errors: []
    };
  },
  created: function () { },
  methods: {
    submit: function () {
      axios.post("/posts", this.newPostParams).then(response => {
        console.log(response.data);
        this.$router.push("/login");
      })
        .catch((error) => {
          this.errors = error.response.data.errors;
        });
    },
  },
};
</script>

<template>
  <div class="signup">
    <form v-on:submit.prevent="submit()">
      <h1>New Post</h1>
      <ul>
        <li v-for="error in errors" v-bind:key="error">{{  error  }}</li>
      </ul>
      <div>
        <label>Title:</label>
        <input type="text" v-model="newPostParams.title" />
      </div>
      <div>
        <label>User ID:</label>
        <input type="integer" v-model="newPostParams.user_id" />
      </div>
      <div>
        <label>Body:</label>
        <input type="text" v-model="newPostParams.body" />
      </div>
      <div>
        <label>Image Url:</label>
        <input type="text" v-model="newPostParams.image_url" />
      </div>
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>
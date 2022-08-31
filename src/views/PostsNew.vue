<script>
import axios from 'axios';

export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      newPostParams: {
        body: ""
      },
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
        <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
      </ul>
      <div>
        <b><label>Title:</label></b>
        <input type="text" v-model="newPostParams.title" />
      </div>
      <div>
        <b><label>User ID:</label></b>
        <input type="integer" v-model="newPostParams.user_id" />
      </div>
      <div>
        <b><label>Body:</label></b>
        <input type="text" v-model="newPostParams.body" />
        <small v-if="newPostParams.body.length <= 200">
          {{ 200 - newPostParams.body.length }}
        </small>
        <small v-if="newPostParams.body.length > 200">
          Body is to long, please shorten!
        </small>
      </div>
      <div>
        <b><label>Image Url:</label></b>
        <input type="text" v-model="newPostParams.image_url" />
      </div>
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>
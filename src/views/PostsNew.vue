<script>
export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      newUserParams: {},

    };
  },
  created: function () { },
  methods: {
    returnTest: function () {
      return this.test;
    }
  },
};
</script>

<template>
  <div class="signup">
    <form v-on:submit.prevent="submit()">
      <h1>Signup</h1>
      <ul>
        <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
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
        <label>Image URL:</label>
        <input type="text" v-model="newPostParams.image" />
      </div>
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>
<style>
</style>
<template>
  <div class="container">
    <form action="" @submit.prevent="createPost">
      <div>
        <label for="userId"></label>
        <input id="userId" v-model="formData.userId" name="" placeholder="ID" type="text">
      </div>
      <div>
        <label for="title"></label>
        <input id="title" v-model="formData.title" name="" placeholder="Title" type="text">
      </div>
      <div>
        <label for="body"></label>
        <input id="body" v-model="formData.body" name="" placeholder="Post" type="text">
      </div>
      <div class="button">
        <button class="btn btn-primary">CREATE POST</button>
        <button class="btn btn-primary">
          <nuxt-link to="/">HOME</nuxt-link>
        </button>
      </div>
    </form>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "CreatePost",
  data() {
    return {
      formData: {
        userId: "",
        title: "",
        body: ""
      },
    }
  },

  methods: {
    createPost() {
      axios.post('https://jsonplaceholder.typicode.com/posts', this.formData)
        .then(response => console.log(response))
        .catch(error => console.error())
    }
  }
}
</script>

<style>


form {
  width: 500px;
  margin: 0px auto 0px auto;
  padding: 10px;
  border-radius: 5px;
  background-color: rgba(0, 0, 0, 0.05);
}

input {
  width: 100%;
  padding: 12px 20px;
  margin: 2px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

button {
  margin: 50px 20px;
}

.button {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
}


button a {
  color: #ffffff;
}


.btn-primary a:hover {
  color: #ffffff;
  text-decoration: none;
}
</style>

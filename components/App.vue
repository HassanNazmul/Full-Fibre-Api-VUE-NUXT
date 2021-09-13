<template>
  <div class="container">
    <div class="button">
      <button class="btn btn-primary" @click="getPosts">VIEW POST</button>
      <button class="btn btn-primary">
        <nuxt-link to="/newpost">CREATE POST</nuxt-link>
      </button>
    </div>

    <div class="post">
      <div v-for="post in posts" :key="post.id">
        <h3 class="post-title">{{ post.id }}.{{ post.title }}</h3>
        <p class="post-body">{{ post.body }}</p>
        <hr/>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'PostList',
  data() {
    return {
      posts: [],
    }
  },
  methods: {
    getPosts() {
      axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(response => {
          console.log(response.data)
          this.posts = response.data
        })
        .then((error) => {
          console.log(error)
        })
    }
  }
}
</script>

<style>
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

.post {
  padding: 30px 0;
}

.post-title {
  font-family: Roboto;
  font-size: 22px;
  font-weight: 500;
  padding-top: 10px;
  text-transform: capitalize;
}

.post-body {
  font-size: 16px;
  text-transform: capitalize;
}

</style>

<template>
  <div id="app">
    <H2>FULL FIBRE API</H2>
    <PostList/>
  </div>
</template>

<script>
import PostList from './PostList.vue'
export default {
    name: 'App',
    components: {
      PostList
    },
}
</script>

<style>
#app {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    text-align: center;
    margin-top: 50px;
}
</style>

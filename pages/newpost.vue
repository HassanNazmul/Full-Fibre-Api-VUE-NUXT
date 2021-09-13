<template>
  <div>
    <Heading/>
    <div class="container">
      <CreatePost/>
    </div>
  </div>
</template>

<script>
import CreatePost from "../components/CreatePost";

export default {
  components: {CreatePost}
}
</script>

<style>
.container {
  padding-top: 50px;
}
</style>

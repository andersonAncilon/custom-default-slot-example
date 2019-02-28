<template>
  <div>
    <PostList v-for="post in posts" :key="post.id" :post="post">
      <slot :myPost="post"></slot>
    </PostList>
  </div>
</template>

<script>
import PostList from "./PostList";

export default {
  components: {
    PostList
  },
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
};
</script>

<style scoped>
</style>
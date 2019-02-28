<template>
  <div class="post-list">
    <slot>
        <h1>Default Slot</h1>
        <h2>{{ post.title }}</h2>
        <p>{{ post.content }}</p>
        <a href="#">{{ post.author }}</a>
    </slot>
  </div>
</template>

<script>
export default {
    props: {
        post: {
            type: Object,
            required: true
        }
    }
};
</script>

<style scoped>
    .post-list {
        margin-bottom: 15px;
        background-color: #eee;
    }
</style>
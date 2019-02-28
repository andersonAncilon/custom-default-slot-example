<template>
  <div id="app">
    <Post :posts="posts" v-slot="{ myPost }">
      <template v-if="show">
        <h1>Custom Slot</h1>
        <template>
          <h2>{{ myPost.title }}</h2>
        </template>

        <template>
          <p>{{ myPost.content }}</p>
        </template>

        <template>
          <a href="#">{{ myPost.author }}</a>
        </template>
      </template>
    </Post>
    <button class="my-button" @click="show = !show">Change default/custom slot</button>
  </div>
</template>

<script>
import Post from "./components/Post";

export default {
  name: "app",
  components: {
    Post
  },
  data() {
    return {
      show: false,
      posts: [
        {
          id: 1,
          title: "Estudando VueJS",
          content: "Aprendendo a utilizar slots dinamicamente",
          author: "Anderson Ancilon"
        },
        {
          id: 2,
          title: "Estudando VueJS 2",
          content: "Aprendendo a utilizar slots dinamicamente",
          author: "Anderson Ancilon"
        }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.my-button {
  height: 50px;
  border-radius: 5px;
  background-color: lightseagreen;
  font-size: 15px;
  font-weight: bold;
  cursor: pointer;
}

.my-buton :hover {
  background-color: lightcoral;
}
</style>

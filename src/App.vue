<template>
  <div class="app">
    <post-form/>
    <post-list/>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        { id: 1, title: 'Title 1', body: 'Body 1' },
        { id: 2, title: 'Title 2', body: 'Body 2' },
        { id: 3, title: 'Title 3', body: 'Body 3' },
        { id: 4, title: 'Title 4', body: 'Body 4' },
        { id: 5, title: 'Title 5', body: 'Body 5' },
        { id: 6, title: 'Title 6', body: 'Body 6' },
      ],
      title: '',
      body: '',
    }
  },
    methods: {
    deletePost() {
      this.posts.pop();
    },
    createPost() {
      this.posts.push({ id: this.posts.length + 1, title: `${this.title} ${this.posts.length + 1}`, body: `${this.body} ${this.posts.length + 1}` });
      this.title = '';
      this.body = '';
    }
  }
}

</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}

</style>
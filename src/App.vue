<template>
  <div class="app">
    <form @submit.prevent>
      <h4>Create post:</h4>
      <input v-bind:value="title" @input="title = $event.target.value" class="input" type="text" placeholder="Name">
      <input v-bind:value="body" @input="body = $event.target.value" class="input" type="text" placeholder="Description">
      <button class="btn" @click="createPost">Create</button>
    </form>
    <div v-for="post in posts">
      <div class="post">
        <div><strong>Name:</strong>{{ post.title }}</div>
        <div><strong>Description:</strong>{{ post.body }}</div>
      </div>
    </div>
    <button class="btn" @click="deletePost">Delete post</button>
  </div>
</template>

<script>
export default {
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

.post {
  padding: 15px;
  border: 2px solid teal ;
  margin-top: 15px;
}

form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>
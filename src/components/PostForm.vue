<template scope>
  <form @submit.prevent>
    <h4>Create post:</h4>
    <input v-model="post.title" class="input" type="text" placeholder="Name">
    <input v-model="post.body" class="input" type="text" placeholder="Description">
    <button @click="createPost" class="btn">Create</button>
  </form>
  <button @click="deletePost" class="btn">Delete post</button>
</template>
  

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost(e) {
      this.$emit('create', this.post),
      this.post = {
        title: '',
        body: ''
      }
    },
    deletePost(e) {
      this.$emit('delete')
    }
  }
}
</script>

<style>
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
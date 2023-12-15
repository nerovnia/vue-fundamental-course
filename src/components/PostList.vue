<template scope>
  <div v-for="post in posts">
    <div class="post">
      <div><strong>Name:</strong>{{ post.title }}</div>
      <div><strong>Description:</strong>{{ post.body }}</div>
  </div>
  </div>
</template>
  

<script></script>

<style>
.post {
  padding: 15px;
  border: 2px solid teal ;
  margin-top: 15px;
}
</style>
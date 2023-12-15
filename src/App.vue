<template>
  <div>Work!</div>
      <div>Likes:<span>{{ likes }}</span></div>
      <div>Dislikes:<span>{{ dislikes }}</span></div>
      <button @click="addLike">likes</button>
    <button @click="addDislike">Dislikes</button>
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
      dislikes: 5
    }
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislikes += 1;
    },
  }
}

</script>

<style>

</style>